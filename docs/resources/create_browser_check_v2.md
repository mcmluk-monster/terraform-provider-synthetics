---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "synthetics_create_browser_check_v2 Resource - terraform-provider-synthetics"
subcategory: ""
description: |-
  
---

# synthetics_create_browser_check_v2 (Resource)



## Example Usage

```terraform
resource "synthetics_create_browser_check_v2" "browser_v2_foo_check" {
  test {
    active = true
    device_id = 1  
    frequency = 15
    location_ids = ["aws-us-east-1"]
    name = "Terraform - Browser V2 Checkaroo"
    scheduling_strategy = "round_robin"
    url_protocol = "https://"
    start_url = "www.splunk.com"
    transactions {
      name = "First Synthetic transaction"
      steps {
        name                 = "01 Go to URL"
        type                 = "go_to_url"
        url                  = "https://www.splunk.com"
        wait_for_nav         = true
      }
      steps {
        name                 = "02 fill in fieldz"
        selector             = "beep"
        selector_type        = "id"
        type                 = "enter_value"
        value                = "{{env.beep-var}}"
        wait_for_nav         = false
      }
      steps {
        name                 = "03 click"
        selector             = "clicky"
        selector_type        = "id"
        type                 = "click_element"
        wait_for_nav         = true
      }
      steps {
        name                 = "04 accept---Alert"
        type                 = "accept_alert"
        wait_for_nav         = false
      }
      steps {
        name                 = "05 Select-val-text"
        option_selector      = "sdad"
        option_selector_type = "text"
        selector             = "textzz"
        selector_type        = "id"
        type                 = "select_option"
        wait_for_nav         = false
      }
      steps {
        name                 = "06 Select-Val-Val"
        option_selector      = "{{env.beep-var}}"
        option_selector_type = "value"
        selector             = "valz"
        selector_type        = "id"
        type                 = "select_option"
        wait_for_nav         = false
      }
      steps {
        name                 = "07 Select-Val-Index"
        option_selector      = "{{env.beep-var}}"
        option_selector_type = "index"
        selector             = "selectionz"
        selector_type        = "id"
        type                 = "select_option"
        wait_for_nav         = false
      }
      steps {
        name                 = "08 Save as text"
        selector             = "beepval"
        selector_type        = "link"
        type                 = "store_variable_from_element"
        variable_name        = "{{env.terraform-test-foo-301}}"
        wait_for_nav         = false
      }
      steps {
        name                 = "09 Save JS2 return Val"
        type                 = "store_variable_from_javascript"
        value                = "sdasds"
        variable_name        = "{{env.terraform-test-foo-301}}"
        wait_for_nav         = true
      }
      steps {
        name                 = "010 Run JS"
        type                 = "run_javascript"
        value                = "beeeeeeep"
        wait_for_nav         = true
      }
    }
    transactions {
      name = "2nd Synthetic transaction"
      steps {
        name                 = "Go to other URL"
        type                 = "go_to_url"
        url                  = "https://www.splunk.com"
        wait_for_nav         = true
      }
      steps {
        name                 = "fill in more fields field"
        selector             = "beep"
        selector_type        = "id"
        type                 = "enter_value"
        value                = "{{env.beep-var}}"
        wait_for_nav         = false
      }
    }
    advanced_settings {
      verify_certificates = false
      user_agent = "Mozilla/5.0 (X11; Linux x86_64; Splunk Synthetics) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4472.114 Safari/537.36"
      authentication {
        username = "batmab"
        password = "{{env.beep-var}}"
      }
      headers {
        name = "superstar-machine"
        value = "\"taking it too the staaaaars\""
        domain = "asdasd.batman.com"
      }
      cookies {
        key = "sda"
        value = "sda"
        domain = "asd.com"
        path = "/asd"
      }
      cookies {
        key = "yes"
        value = "no"
        domain = "zodiak.com"
        path = "/Edlesley"
      }
      host_overrides {
        source = "asdasd.com"
        target = "whost.com"
        keep_host_header = false
      }
      host_overrides {
        source = "92.2.2.2"
        target = "91.1.1.1"
        keep_host_header = true
      }
    }
  }    
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `test` (Block Set, Min: 1) (see [below for nested schema](#nestedblock--test))

### Read-Only

- `id` (String) The ID of this resource.

<a id="nestedblock--test"></a>
### Nested Schema for `test`

Required:

- `name` (String)
- `start_url` (String)
- `transactions` (Block List, Min: 1) (see [below for nested schema](#nestedblock--test--transactions))
- `url_protocol` (String)

Optional:

- `active` (Boolean)
- `advanced_settings` (Block Set) (see [below for nested schema](#nestedblock--test--advanced_settings))
- `device_id` (Number)
- `frequency` (Number)
- `location_ids` (List of String)
- `scheduling_strategy` (String)

<a id="nestedblock--test--transactions"></a>
### Nested Schema for `test.transactions`

Required:

- `steps` (Block List, Min: 1) (see [below for nested schema](#nestedblock--test--transactions--steps))

Optional:

- `name` (String)

<a id="nestedblock--test--transactions--steps"></a>
### Nested Schema for `test.transactions.steps`

Required:

- `wait_for_nav` (Boolean)

Optional:

- `action` (String)
- `name` (String)
- `option_selector` (String)
- `option_selector_type` (String)
- `options` (Block Set) (see [below for nested schema](#nestedblock--test--transactions--steps--options))
- `selector` (String)
- `selector_type` (String)
- `type` (String)
- `url` (String)
- `value` (String)
- `variable_name` (String)

<a id="nestedblock--test--transactions--steps--options"></a>
### Nested Schema for `test.transactions.steps.options`

Optional:

- `url` (String)




<a id="nestedblock--test--advanced_settings"></a>
### Nested Schema for `test.advanced_settings`

Optional:

- `authentication` (Block Set) (see [below for nested schema](#nestedblock--test--advanced_settings--authentication))
- `cookies` (Block Set) (see [below for nested schema](#nestedblock--test--advanced_settings--cookies))
- `headers` (Block Set) (see [below for nested schema](#nestedblock--test--advanced_settings--headers))
- `host_overrides` (Block Set) (see [below for nested schema](#nestedblock--test--advanced_settings--host_overrides))
- `user_agent` (String)
- `verify_certificates` (Boolean)

<a id="nestedblock--test--advanced_settings--authentication"></a>
### Nested Schema for `test.advanced_settings.authentication`

Optional:

- `password` (String)
- `username` (String)


<a id="nestedblock--test--advanced_settings--cookies"></a>
### Nested Schema for `test.advanced_settings.cookies`

Optional:

- `domain` (String)
- `key` (String)
- `path` (String)
- `value` (String)


<a id="nestedblock--test--advanced_settings--headers"></a>
### Nested Schema for `test.advanced_settings.headers`

Optional:

- `domain` (String)
- `name` (String)
- `value` (String)


<a id="nestedblock--test--advanced_settings--host_overrides"></a>
### Nested Schema for `test.advanced_settings.host_overrides`

Optional:

- `keep_host_header` (Boolean)
- `source` (String)
- `target` (String)

