# Canvas LMS GraphQL API

Canvas exposes a GraphQL endpoint at `/api/graphql` that provides access to the Canvas object graph. The API supports queries and mutations for courses, users, enrollments, assignments, submissions, modules, discussion topics, outcomes, account hierarchies, and more. Permissions mirror the Canvas REST API.

**Endpoint:** `https://<canvas-install-url>/api/graphql`

**Explorer:** `https://<canvas-install-url>/graphiql` (hosted GraphiQL)

**Documentation:** https://canvas.instructure.com/doc/api/file.graphql.html

**Authentication:** OAuth2 Bearer token — same developer keys and personal access tokens used by the REST API.

## Key Features

- Relay-style cursor pagination with `Connection`, `Edge`, and `PageInfo` types
- Global opaque `Node` IDs (base64-encoded `type:id`) for cross-type lookups
- Mutations for submissions, grading, discussion entries, and module management
- Introspection enabled on self-hosted and Free-for-Teacher instances at `/api/graphql`
- Permissions checked per-field using the same Canvas permission model as the REST API

## Schema Overview

The schema (`canvas-lms-schema.graphql`) covers 70+ named types organized into the following domains:

### Account Hierarchy
- `Account` — root or sub-account node
- `SubAccount` — child account
- `Term` — enrollment term (semester, quarter, year)

### People
- `User` — Canvas user account
- `UserProfile` — extended bio and preferences
- `Enrollment` — role-scoped membership in a course
- `Grade` — computed grade summary for an enrollment

### Courses
- `Course` — primary learning container
- `CoursePermissions` — resolved permission set for the current user
- `Section` — roster sub-group within a course

### Assignments & Submissions
- `Assignment` — a gradeable task
- `AssignmentGroup` — weighted grouping of assignments
- `AssignmentGroupRules` — drop-lowest / drop-highest rules
- `AssignmentOverride` — differentiated due dates for individuals, sections, or groups
- `Submission` — a student's attempt
- `SubmissionHistory` — historical attempt records
- `SubmissionComment` — instructor/student feedback thread on a submission
- `ExternalToolTagAttributes` — LTI tool attachment on an assignment
- `RubricSettings` — inline rubric configuration

### Rubrics
- `Rubric` — reusable assessment template
- `RubricCriterion` — a row within a rubric
- `RubricRating` — a level within a criterion
- `RubricAssociation` — links a rubric to an assignment
- `RubricAssessment` — a completed scoring event
- `RubricCriterionAssessment` — per-criterion score and comment

### Grading
- `GradingPeriod` — a quarter, semester, or marking period
- `GradingStandard` — letter-grade scale
- `GradingSchemeEntry` — one row in a grading scheme

### Quizzes
- `Quiz` — Classic Quizzes quiz container
- `QuizQuestion` — individual question
- `QuizAnswer` — a possible answer choice
- `QuizSubmission` — a student's quiz attempt

### Discussions & Announcements
- `Discussion` — a discussion topic
- `DiscussionEntry` — a reply or threaded post
- `Announcement` — a locked broadcast topic

### Modules & Pages
- `Module` — sequential content container
- `ModuleItem` — a content item within a module
- `ModuleCompletionRequirement` — rule required to complete an item
- `ContentPage` — a Canvas wiki page

### Files & Media
- `File` — an uploaded attachment
- `Folder` — a directory container for files
- `LockInfo` — lock state metadata
- `Media` — a video or audio media object

### Groups
- `Group` — a collaborative team
- `GroupCategory` — a set of groups (e.g., "Project Teams")
- `GroupMembership` — a user's membership in a group

### Calendar & Todo
- `CalendarEvent` — a scheduled event
- `Todo` — a to-do item for the current user

### Outcomes
- `Outcome` — a learning standard
- `OutcomeGroup` — hierarchical grouping of outcomes
- `OutcomeAlignment` — links an outcome to an assignment
- `OutcomeResult` — a recorded mastery result for a student

### Roles & Permissions
- `Role` — a built-in or custom permission role
- `Permission` — a granular permission entry on a role

### External Tools & Features
- `ExternalTool` — an LTI 1.3 tool configuration
- `FeatureFlag` — a Canvas feature toggle

### Content Management
- `ContentMigration` — a course copy or import job
- `ContentExport` — a Common Cartridge or QTI export job

### SIS
- `SISImport` — a SIS CSV import job

### Conferences & Collaboration
- `ConferenceMeeting` — a web conference (BigBlueButton, Zoom)
- `Collaboration` — a collaborative document (Google Docs, EtherPad)

### Mastery Paths
- `LearningPath` — a mastery path rule on an assignment
- `ScoringRange` — a score band that releases an assignment set
- `AssignmentSet` — a set of assignments released by a scoring range
- `AssignmentSetAssociation` — an assignment within a set

### Pagination
- `PageInfo` — Relay cursor pagination metadata
- `*Connection` / `*Edge` types for every top-level entity

## Example Queries

### Fetch course with sections and enrollments
```graphql
query CourseRoster($courseId: ID!) {
  course(id: $courseId) {
    id
    name
    courseCode
    sections(first: 10) {
      edges {
        node {
          id
          name
          enrollmentCount
        }
      }
    }
    enrollments(first: 50, type: [StudentEnrollment]) {
      edges {
        node {
          id
          type
          user {
            id
            name
            email
          }
          grades {
            currentGrade
            currentScore
          }
        }
      }
    }
  }
}
```

### Fetch assignments with submissions
```graphql
query AssignmentsWithSubmissions($courseId: ID!) {
  course(id: $courseId) {
    assignments(first: 20, orderBy: [due_at]) {
      edges {
        node {
          id
          name
          dueAt
          pointsPossible
          gradingType
          submissions(first: 5) {
            edges {
              node {
                id
                score
                grade
                submittedAt
                workflowState
                user { id name }
              }
            }
          }
        }
      }
    }
  }
}
```

### Post a grade via mutation
```graphql
mutation GradeSubmission($input: PostSubmissionGradeInput!) {
  postSubmissionGrade(input: $input) {
    submission {
      id
      score
      grade
      gradedAt
    }
    errors {
      attribute
      message
    }
  }
}
```

## References

- GraphQL documentation: https://canvas.instructure.com/doc/api/file.graphql.html
- REST API (for permission model reference): https://canvas.instructure.com/doc/api/
- OAuth2 authentication: https://canvas.instructure.com/doc/api/file.oauth.html
- Canvas LMS source (GraphQL schema source): https://github.com/instructure/canvas-lms/tree/master/app/graphql
- Schema file: canvas-lms-schema.graphql
