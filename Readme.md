
# Timeslot.io API

## Get Started

You can simply integrate the [Timeslot.io Widget][widget] or you can follow the instructions below:

[widget]: https://github.com/timeslot/timeslot-widget

1. Create your account at [Timeslot.io](http://timeslot.io/signup).
2. Integrate with our API wrapper for [Node.js][node], [Ruby][ruby], [Python][python], or [PHP][php].
3. Make requests to our API and let your users schedule time slots.

[node]: https://github.com/timeslot/timeslot-node
[ruby]: https://github.com/timeslot/timeslot-ruby
[python]: https://github.com/timeslot/timeslot-python
[php]: https://github.com/timeslot/timeslot-php

## Resources

All resources support standard CRUD routes.

### Schedule

Parameter | Type | Description | Required | Default Value | Possible Values
--- | --- | --- | --- | --- | ---
`id` | String | ID | No | Auto | N/A
`date` | Date | Date | Yes | None | Future dates
`start_time` | Date | Start Time | Yes | None | Future dates
`end_time` | Date | End Time | Yes | None | Future dates
`duration` | Integer | Duration | Yes | None | Any integer in minutes >= 15
`location` | String | Location | No, but yes if `format` is equal to `in-person` | Any valid address, as searchable by Google Maps (e.g. 123 Street, City, State, ZIP).
`repeat` | String | Repeat | No | `once` | `once`, `weekly`, `daily`
`title` | String | Title | No | None | 40 characters
`desc` | String | Description | No | None | 140 characters
`format` | String | Format | No | `in-person` | `in-person`, `skype`, `google-hangout`, `phone`
`cost` | Integer | Cost | No | `0` | Any USD value >= $1.00 in cents, e.g. `100` = $1.00.
`confirm_slots` | Boolean | Confirm slots before accepting to schedule. | No | `false` | `true` or `false`
`email_notifications` | Boolean | Send email notifications | No | `true` | `true` or `false`
`email_reminders` | Boolean | Send email reminders | No | `true` | `true` or `false`
`sms_notifications` | Boolean | Send SMS notifications | No | `true` | `true` or `false`
`sms_reminders` | Boolean | Send SMS reminders | No | `true` | `true` or `false`
`vcf` | Boolean | Send vCards (.vcf) files with emails and SMS messages | No | `true` | `true` or `false`
`cal` | Boolean | Send calendar events (.cal) files with emails and SMS messages | No | `true` | `true` or `false`
`created` | Date | Created | No | Auto | N/A
`updated` | Date | Updated | No | Auto | N/A

### Slots

Parameter | Type | Description | Required | Default Value | Possible Values
--- | --- | --- | --- | --- | ---
`id` | String | ID | No | Auto | N/A
`schedule_id` | String | Schedule ID | Yes | None | Any valid schedule ID
`email` | Email | Email | Yes | None | Any valid email address
`name` | String | Name | Yes | None | 20 characters
`surname` | String | Surname | Yes | None | 20 characters
`phone` | String | Phone Number | Yes | None | Any valid [E164][e164] phone number (e.g. `+16506918337` for US phone number)
`comments` | String | Comments | No | None | 140 characters
`start_time` | Date | Start time | Yes | None | Any valid time between `start_time` plus the `duration` of `schedule_id` OR any valid time between `start_time` and `end_time` that does not overlap with other time slots belonging to `schedule_id` (e.g. this lets you manually override the default `duration` for instances of slots)
`end_time` | Date | End time | No | `start_time` plus `schedule_id`'s `duration` value in minutes | Any valid date that is at least `start_time` plus `schedule_id`'s `duration` long and does not overlap with other time slots belonging to `schedule_id`.
`accepted` | Boolean | Accepted for the schedule | No | `true` if `schedule.confirm_slots` is `false`, else `false` | `true` or `false`
`created` | Date | Created | No | Auto | N/A
`updated` | Date | Updated | No | Auto | N/A

[e164]: http://en.wikipedia.org/wiki/E.164
