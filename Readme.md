
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
`startTime` | Date | Start Time | Yes | None | Future dates
`endTime` | Date | End Time | Yes | None | Future dates
`repeat` | String | Repeat | No | `once` | `once`, `weekly`, `daily`
`title` | String | Title | No | None | 40 characters
`desc` | String | Description | No | None | 140 characters
`format` | String | Format | No | `in-person` | `in-person`, `skype`, `google-hangout`, `phone`
`cost` | String | Cost | No | `0` | Any USD value >= $1.00 in cents, e.g. `100` = $1.00.
`created` | Date | Created | No | Auto | N/A
`updated` | Date | Updated | No | Auto | N/A

### Slots

Parameter | Type | Description | Required | Default Value | Possible Values
--- | --- | --- | --- | --- | ---
`id` | String | ID | No | Auto | N/A
`email` | Email | Email | Yes | None | Any valid email address
`schedule_id` | String | Schedule ID | Yes | None | Any valid schedule ID
`created` | Date | Created | No | Auto | N/A
`updated` | Date | Updated | No | Auto | N/A
