# Playwright to Bugster Test Migration Index

## Overview

This document tracks the migration of Playwright E2E tests to Bugster YAML format specifications.

**Migration Date**: 2025-10-03  
**Total Tests Migrated**: 35  
**Original Playwright Test Files**: 100+  
**Coverage**: Core user workflows and critical business functionality

## Migration Summary by Category

### 🔐 Authentication (`/auth`) - 5 tests
| Test Name | File | Page Path |
|-----------|------|-----------|
| Login with credentials | `login_with_credentials.yaml` | `app/(use-page-wrapper)/auth/login/page.tsx` |
| Two-factor authentication | `two_factor_authentication.yaml` | `app/(use-page-wrapper)/auth/login/page.tsx` |
| New user signup | `signup_new_user.yaml` | `app/(use-page-wrapper)/signup/page.tsx` |
| Password reset flow | `forgot_password_flow.yaml` | `app/(use-page-wrapper)/auth/forgot-password/page.tsx` |
| Logout functionality | `logout_functionality.yaml` | `app/(use-page-wrapper)/auth/logout/page.tsx` |

### 📅 Bookings (`/bookings`) - 5 tests
| Test Name | File | Page Path |
|-----------|------|-----------|
| Create first booking | `create_first_booking.yaml` | `app/(booking-page-wrapper)/[user]/[type]/page.tsx` |
| Reschedule booking | `reschedule_existing_booking.yaml` | `app/(use-page-wrapper)/(main-nav)/bookings/[status]/page.tsx` |
| Cancel booking | `cancel_booking.yaml` | `app/(use-page-wrapper)/(main-nav)/bookings/[status]/page.tsx` |
| Mark no-show | `mark_attendee_no_show.yaml` | `app/(use-page-wrapper)/(main-nav)/bookings/[status]/page.tsx` |
| Multiple guests | `booking_with_multiple_guests.yaml` | `app/(booking-page-wrapper)/[user]/[type]/page.tsx` |

### 🎯 Event Types (`/event_types`) - 5 tests
| Test Name | File | Page Path |
|-----------|------|-----------|
| Create event type | `create_new_event_type.yaml` | `app/(use-page-wrapper)/(main-nav)/event-types/page.tsx` |
| Configure location | `configure_event_location.yaml` | `app/(use-page-wrapper)/(main-nav)/event-types/[type]/page.tsx` |
| Set booking limits | `set_booking_limits.yaml` | `app/(use-page-wrapper)/(main-nav)/event-types/[type]/page.tsx` |
| Duplicate event | `duplicate_event_type.yaml` | `app/(use-page-wrapper)/(main-nav)/event-types/page.tsx` |
| Delete event | `delete_event_type.yaml` | `app/(use-page-wrapper)/(main-nav)/event-types/page.tsx` |

### 🕐 Availability (`/availability`) - 5 tests
| Test Name | File | Page Path |
|-----------|------|-----------|
| Manage working hours | `manage_working_hours.yaml` | `app/(use-page-wrapper)/(main-nav)/availability/page.tsx` |
| Create date override | `create_date_override.yaml` | `app/(use-page-wrapper)/(main-nav)/availability/page.tsx` |
| Delete date override | `delete_date_override.yaml` | `app/(use-page-wrapper)/(main-nav)/availability/page.tsx` |
| Multiple schedules | `create_multiple_schedules.yaml` | `app/(use-page-wrapper)/(main-nav)/availability/page.tsx` |
| Change timezone | `change_timezone.yaml` | `app/(use-page-wrapper)/(main-nav)/availability/page.tsx` |

### ⚙️ Settings (`/settings`) - 5 tests
| Test Name | File | Page Path |
|-----------|------|-----------|
| Update profile | `update_user_profile.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/my-account/profile/page.tsx` |
| Change username | `change_username.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/my-account/profile/page.tsx` |
| Change password | `change_password.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/security/password/page.tsx` |
| Change theme | `change_theme.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/my-account/appearance/page.tsx` |
| Delete account | `delete_account.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/my-account/profile/page.tsx` |

### 👥 Teams (`/teams`) - 5 tests
| Test Name | File | Page Path |
|-----------|------|-----------|
| Create team | `create_new_team.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/teams/new/page.tsx` |
| Invite member | `invite_team_member.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/teams/[id]/members/page.tsx` |
| Team event type | `create_team_event_type.yaml` | `app/(use-page-wrapper)/(main-nav)/event-types/page.tsx` |
| Remove member | `remove_team_member.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/teams/[id]/members/page.tsx` |
| Change member role | `change_member_role.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/teams/[id]/members/page.tsx` |

### 🏢 Organizations (`/organizations`) - 5 tests
| Test Name | File | Page Path |
|-----------|------|-----------|
| Create organization | `create_organization.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/organizations/new/page.tsx` |
| Invite to org | `invite_to_organization.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/organizations/[id]/members/page.tsx` |
| Org team management | `organization_team_management.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/organizations/[id]/teams/page.tsx` |
| Org settings | `organization_settings.yaml` | `app/(use-page-wrapper)/(main-nav)/settings/organizations/[id]/profile/page.tsx` |
| Org domain booking | `organization_booking_on_domain.yaml` | `app/(booking-page-wrapper)/org/[orgSlug]/[user]/[type]/page.tsx` |

## Playwright Tests NOT Yet Migrated

The following test categories from the original Playwright suite have NOT been migrated yet:

### High Priority (Recommended for Next Migration)
- **Webhooks** (`webhook.e2e.ts`) - Webhook configuration and triggers
- **Workflows** (`workflow.e2e.ts`) - Automated workflow creation and management
- **Routing Forms** (`routing-forms/`) - Form creation, routing logic, attribute routing
- **Payment Integration** (`integrations-stripe.e2e.ts`, `payment*.e2e.ts`) - Stripe integration, paid bookings
- **Calendar Integration** (`integrations.e2e.ts`) - Google Calendar, Zoom, etc.

### Medium Priority
- **Managed Events** (`managed-event-types.e2e.ts`) - Enterprise managed event types
- **Booking Questions** (`manage-booking-questions.e2e.ts`) - Custom form fields
- **Out of Office** (`out-of-office.e2e.ts`) - OOO redirects and management
- **Seats** (`booking-seats.e2e.ts`) - Multi-attendee bookings with seats
- **Recurring Events** - Recurring booking patterns
- **Insights** (`insights*.e2e.ts`) - Analytics and reporting

### Lower Priority
- **Embed** (`embed-code-generator.e2e.ts`) - Embed widget generation
- **SAML/OAuth** (`saml.e2e.ts`, `oidc.e2e.ts`, `oauth-provider.e2e.ts`) - Enterprise SSO
- **Impersonation** (`impersonation.e2e.ts`) - Admin user impersonation
- **Trial** (`trial.e2e.ts`) - Trial period management
- **Localization** (`locale.e2e.ts`) - i18n functionality
- **Performance** (`booking-race-condition.e2e.ts`, `booking-duplicate-api-calls.e2e.ts`) - Performance tests

## Migration Criteria

Tests were selected for migration based on:

1. **User Impact**: Features used by majority of users
2. **Business Critical**: Core functionality required for app operation
3. **Frequency**: Most commonly executed user workflows
4. **Stability**: Well-established features with clear expected behavior
5. **Independence**: Tests that can run independently without complex setup

## Bugster Format Compliance

All migrated tests follow the Bugster specification:

✅ **Required Fields**: All tests include `name`, `page`, `page_path`, `task`, `steps`, `expected_result`  
✅ **File Naming**: snake_case format (e.g., `login_with_credentials.yaml`)  
✅ **Directory Structure**: Mirrors application feature hierarchy  
✅ **Page Paths**: Relative paths from web app root  
✅ **Test Limits**: Maximum 5 tests per feature category  

## Usage

These YAML specifications serve as:

1. **Test Documentation**: Human-readable test scenarios
2. **Bugster Input**: Machine-readable specifications for test generation
3. **QA Reference**: Manual testing guides
4. **Regression Suite**: Core functionality verification

## Next Steps

To continue migration:

1. Review unmigrated test categories above
2. Prioritize based on business needs
3. Select up to 5 representative tests per category
4. Follow existing YAML format and structure
5. Update this index with new additions

## Related Files

- **Bugster Config**: `.bugster/config.yaml`
- **Existing Tests**: `.bugster/tests/(use-page-wrapper)/`
- **Playwright Tests**: `playwright/`
- **Test Generation Rules**: `.cursor/rules/bugster-test-gen.mdc`


