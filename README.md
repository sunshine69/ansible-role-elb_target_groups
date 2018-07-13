elb_target_groups
-----------------

The `elb_target_groups` role creates the target groups used
by a load balancer

# Variables

* `target_groups` - a list of target groups to create

Examples
```
target_groups:
  default:
    name: "{{ env }}-default-{{ role_type }}-tg"
    protocol: https
  http:
    name: "{{ env }}-http-{{ role_type }}-tg"
    protocol: http
```

The possible keys for each TG (such as name and protocol above) has the exact
parameter name of the ansible module `elb_target_group` as it will be passed
through.
