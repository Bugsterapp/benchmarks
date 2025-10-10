# Migrated Playwright Tests to Bugster Format

This directory contains Playwright E2E tests that have been migrated to the Bugster YAML specification format.

## Directory Structure

The tests are organized by feature area to match the application's functionality:

### `/auth` - Authentication & Authorization
- Login with credentials
- Two-factor authentication
- User signup
- Password reset flow
- Logout functionality

### `/bookings` - Booking Management
- Create new bookings
- Reschedule existing bookings
- Cancel bookings
- Mark attendees as no-show
- Multiple guest bookings

### `/event_types` - Event Type Configuration
- Create new event types
- Configure locations (video conferencing, etc.)
- Set booking limits
- Duplicate event types
- Delete event types

### `/availability` - Schedule Management
- Manage working hours
- Create date overrides
- Delete date overrides
- Multiple schedules
- Timezone configuration

### `/settings` - User Settings
- Update profile information
- Change username
- Change password
- Theme preferences
- Account deletion

### `/teams` - Team Collaboration
- Create teams
- Invite team members
- Create team event types
- Remove team members
- Change member roles

### `/organizations` - Organization Management
- Create organizations
- Invite to organization
- Organization team management
- Organization settings
- Organization domain bookings

## Migration Notes

- **Total Tests Migrated**: 35 tests covering core functionality
- **Original Playwright Tests**: 100+ test files
- **Selection Criteria**: Tests were selected based on:
  - Core user workflows
  - Critical business functionality
  - Most commonly used features
  - Representative coverage of each feature area

## File Naming Convention

All test files follow snake_case naming:
- ✅ `login_with_credentials.yaml`
- ✅ `create_new_event_type.yaml`
- ❌ `loginWithCredentials.yaml` (camelCase not used)

## YAML Structure

Each test file contains:
- `name`: Descriptive test name
- `page`: Route path for the test
- `page_path`: Relative file path to the actual page component
- `task`: Clear objective of what's being tested
- `steps`: Numbered list of actions and verifications
- `expected_result`: Success criteria

## Running Tests

These YAML specifications can be used by Bugster to generate and execute automated tests. Refer to the Bugster documentation for execution instructions.

## Coverage Limitations

This migration focuses on the most critical user paths. Additional test coverage areas from the original Playwright suite that may require future migration include:

- Advanced workflow automations
- Routing forms
- Webhook integrations
- Payment processing
- SAML/OAuth authentication
- Embed functionality
- API integrations
- Performance testing scenarios

## Contributing

When adding new tests:
1. Follow the existing directory structure
2. Use snake_case for file names
3. Include all required YAML fields
4. Limit to 5 tests per feature unless explicitly needed
5. Ensure page_path is relative to the web app root


