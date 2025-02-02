---
title: "Augment templates"
date: 2024-04-17T14:00:14-07:00
# Change draft status to false to publish doc
draft: false
# Description
# Add a short description (150 chars) for the doc. Include keywords for SEO.
# The description text appears in search results and at the top of the doc.
description: ""
# Assign weights in increments of 100
weight: 120
toc: true
tags: [ "docs" ]
# Create a new entry in the Jira DOCS Catalog and add the ticket ID (DOCS-<number>) below
docs: "DOCS-1656"
# Taxonomies
# These are pre-populated with all available terms for your convenience.
# Remove all terms that do not apply.
categories: ["installation", "platform management", "load balancing", "api management", "service mesh", "security", "analytics"]
doctypes: ["concept"]
journeys: ["researching", "getting started", "using", "renewing", "self service"]
personas: ["devops", "netops", "secops", "support"]
versions: []
authors: []
---

## Overview {#augmenting-global-default-base-template}

Using augment templates in F5 NGINX Instance Manager, administrators and developers can customize NGINX configurations beyond the foundational settings of the F5 Global Default Base template. You can use the augment template to add specific features like OIDC authentication, or segment (compartmentalize) configuration elements like location and server blocks. Augment templates can be combined with a base template to build upon it or applied directly to an existing NGINX configuration.

## Understanding augment templates

Augment templates add specific features or modify existing configurations generated by the base template. They can be categorized into two main types:

- **Feature augments**: Add specific features such as caching, authentication, or rate limiting to the NGINX configuration.
- **Segment augments**: Modify or add configuration segments, such as additional server blocks, location directives, or upstream definitions.

## How to use augment templates

{{<call-out "tip" "Deploying config templates">}}<i class="far fa-file-code" aria-hidden="true"></i>
 For instructions on setting up and deploying config templates, including augment templates, see [Manage NGINX Configs with Templates]({{< relref "/nim/nginx-configs/config-templates/how-to/manage-nginx-configs-with-templates.md" >}}).{{</call-out>}}

1. **Identify needs**: Determine the additional functionalities or configuration segments needed beyond the base template. This could include specific NGINX modules, security enhancements, or custom routing requirements.

2. **Select or create augments**: Choose from existing augment templates provided by NGINX Instance Manager or create custom augment templates to meet your specific needs. Custom augment templates can be developed by defining JSON schemas and corresponding `.tmpl` files, similar to the base template.

3. **Apply augments**: Use the NGINX Instance Manager interface to apply the selected augment templates to your NGINX configuration. This can be done by specifying the augment templates to be included when [previewing and generating the config]({{< relref "/nim/nginx-configs/config-templates/how-to/manage-nginx-configs-with-templates.md#preview-generate-config" >}}).

4. **Customize inputs**: Provide any required inputs for the augment templates. This may involve specifying parameters such as paths, server names, or authentication keys, depending on the functionality being added.

5. **Generate and deploy**: Once the augment templates and their inputs have been defined, generate the final NGINX configuration. Review the generated configuration to ensure it meets your requirements before deploying it to your NGINX instances.


## Benefits of using augment templates

- **Modularity**: Augment templates allow for a modular approach to configuring NGINX, enabling users to mix and match features as needed without altering the base configuration. This modularity extends to role-based access control (RBAC), allowing administrators to define specific permissions for who can modify and submit these templates.
- **Flexibility**: By separating specific functionalities into augment templates, configurations can be easily customized and updated to adapt to changing requirements.
- **Simplification**: Augments abstract the complexity of NGINX configuration directives, offering a simplified interface for adding features and making modifications.
- **Reusability**: Augment templates can be reused across different NGINX configurations, promoting consistency and efficiency in managing NGINX instances.

### Best practices for augmenting configurations

- **Test augments separately**: Before applying augment templates to production configurations, test them in a separate environment to ensure they function as expected.
- **Documentation**: Document the purpose and inputs of custom augment templates to facilitate understanding and usage by other team members.

---

## Additional Templating Resources

{{< include "nim/templates/additional-templating-resources.md" >}}