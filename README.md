elb_target_groups
-----------------

The `elb_target_groups` role creates the target groups used
by a load balancer

# Variables

Variables are from the standard lb_target_group param name and pick up from the `target_groups` structure. It has some
default value with the same paraname with prefix `loadbalancer_target_group_`. Example below:

* `target_groups` - a list of target groups to create
* `loadbalancer_target_group_port` - port on which the target group listens
* `loadbalancer_target_group_protocol` - protocol on which the target group listens
* `loadbalancer_target_group_connection_draining` - period in seconds until connections
  are forceably torn down

etc..


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
