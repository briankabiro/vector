---
description: Accepts `log` and `metric` events and allows you to remove one or more event fields.
---

<!--
     THIS FILE IS AUTOOGENERATED!

     To make changes please edit the template located at:

     scripts/generate/templates/docs/usage/configuration/transforms/remove_fields.md.erb
-->

# remove_fields transform

![][images.remove_fields_transform]


The `remove_fields` transform accepts [`log`][docs.log_event] and [`metric`][docs.metric_event] events and allows you to remove one or more event fields.

## Config File

{% code-tabs %}
{% code-tabs-item title="vector.toml (example)" %}
```coffeescript
[transforms.my_remove_fields_transform_id]
  type = "remove_fields" # must be: "remove_fields"
  inputs = ["my-source-id"]
  fields = ["field1", "field2"]
```
{% endcode-tabs-item %}
{% code-tabs-item title="vector.toml (schema)" %}
```coffeescript
[transforms.<transform-id>]
  type = "remove_fields"
  inputs = ["<string>", ...]
  fields = ["<string>", ...]
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Options

| Key  | Type  | Description |
|:-----|:-----:|:------------|
| **REQUIRED** | | |
| `type` | `string` | The component type<br />`required` `enum: "remove_fields"` |
| `inputs` | `[string]` | A list of upstream [source][docs.sources] or [transform][docs.transforms] IDs. See [Config Composition][docs.config_composition] for more info.<br />`required` `example: ["my-source-id"]` |
| `fields` | `[string]` | The field names to drop.<br />`required` `example: ["field1", "field2"]` |

## How It Works

### Environment Variables

Environment variables are supported through all of Vector's configuration.
Simply add `${MY_ENV_VAR}` in your Vector configuration file and the variable
will be replaced before being evaluated.

You can learn more in the [Environment Variables][docs.configuration.environment-variables]
section.

## Troubleshooting

The best place to start with troubleshooting is to check the
[Vector logs][docs.monitoring_logs]. This is typically located at
`/var/log/vector.log`, then proceed to follow the
[Troubleshooting Guide][docs.troubleshooting].

If the [Troubleshooting Guide][docs.troubleshooting] does not resolve your
issue, please:

1. Check for any [open sink issues][url.remove_fields_transform_issues].
2. [Search the forum][url.search_forum] for any similar issues.
2. Reach out to the [community][url.community] for help.


### Alternatives

Finally, consider the following alternatives:

* [`add_fields` transform][docs.add_fields_transform]

## Resources

* [**Issues**][url.remove_fields_transform_issues] - [enhancements][url.remove_fields_transform_enhancements] - [bugs][url.remove_fields_transform_bugs]
* [**Source code**][url.remove_fields_transform_source]


[docs.add_fields_transform]: ../../../usage/configuration/transforms/add_fields.md
[docs.config_composition]: ../../../usage/configuration/README.md#composition
[docs.configuration.environment-variables]: ../../../usage/configuration#environment-variables
[docs.log_event]: ../../../about/data-model.md#log
[docs.metric_event]: ../../../about/data-model.md#metric
[docs.monitoring_logs]: ../../../usage/administration/monitoring.md#logs
[docs.sources]: ../../../usage/configuration/sources
[docs.transforms]: ../../../usage/configuration/transforms
[docs.troubleshooting]: ../../../usage/guides/troubleshooting.md
[images.remove_fields_transform]: ../../../assets/remove_fields-transform.svg
[url.community]: https://vector.dev/community
[url.remove_fields_transform_bugs]: https://github.com/timberio/vector/issues?q=is%3Aopen+is%3Aissue+label%3A%22Transform%3A+remove_fields%22+label%3A%22Type%3A+Bug%22
[url.remove_fields_transform_enhancements]: https://github.com/timberio/vector/issues?q=is%3Aopen+is%3Aissue+label%3A%22Transform%3A+remove_fields%22+label%3A%22Type%3A+Enhancement%22
[url.remove_fields_transform_issues]: https://github.com/timberio/vector/issues?q=is%3Aopen+is%3Aissue+label%3A%22Transform%3A+remove_fields%22
[url.remove_fields_transform_source]: https://github.com/timberio/vector/tree/master/src/transforms/remove_fields.rs
[url.search_forum]: https://forum.vector.dev/search?expanded=true
