---
docs: 
doctypes:
    - task
tags:
    - docs
title: Add a file in a configuration
toc: true
weight: 400
---


## Overview

This guide explains how to add files in the F5 NGINX One Console. While you can manage files in the CLI, the NGINX One Console supports editing in
a UI that resembles an Integrated Development Environment (IDE), with recommendations.

## Before you start

Before you add files in your configuration, ensure:

- You have access to the NGINX One Console.
- NGINX instances are properly registered with NGINX One Console

## Important considerations

If your instance is a member of a Config Sync Group, changes that you make may be synchronized to other instances in that group.
For more information, see how you can [Manage Config Sync Groups]({{< relref "/nginx-one/how-to/config-sync-groups/manage-config-sync-groups.md" >}}).

## Add a file

You can use the NGINX One Console to add a file to a specific instance. To do so:

1. Select the instance to manage.
1. Select the **Configuration** tab.

   {{< tip >}}

   From this window, select the file of your choice. If you want to delete this
   file, Select **Edit Configuration** and select the Trash icon.

   If this was a mistake, a revert button appears. But do not wait. As noted in
   one of the UI messages, "This action cannot be undone once you publish the
   configuration."

   {{< /tip >}}

1. Select **Edit Configuration**.
1. In the **Edit Configuration** window that appears, select **Add File**.

You now have multiple options, described in the sections which follow.

### New Configuration File

Enter the name of the desired configuration file, such as `abc.conf` and select **Add**. The configuration file appears in the **Edit Configuration** window.

### New SSL Certificate or CA Bundle

First you can select the toggle to allow NGINX One Console to manaage the new certificate or bundle.

<!-- Candidate for an "include". Common content with add-file.md -->
In the screen that appears, you can add a certificate name. If you don't add a name, NGINX One will add a name for you, based on the expiration date for the certificate.

You can add certificates in the following formats:

- **SSL Certificate and Key**
- **CA Certificate Bundle**

In each case, you can upload files directly, or enter the content of the certificates in a text box. Once you upload these certificates, you'll see:

- **Certificate Details**, with the Subject Name, start and end dates. 
- **Key Details**, with the encryption key size and algorithm, such as RSA

  {{< tip >}}

  Make sure to specify the path to your certificate in your NGINX configuration,
  with the `ssl_certificate` and `ssl_certificate_key` directives.

  {{< /tip >}}
<!-- end potential "include" -->

### Existing SSL Certificate or CA Bundle

With this option, You can incorporate [Managed certificates]({{< relref "/nginx-one/how-to/certificates/manage-certificates.md#managed-and-unmanaged-certificates" >}}).
In the **Choose Certificate** drop-down, select the managed certificate of your choice, and select **Add**. You can then:

1. Review details of the certificate. The next steps depend on whether the certificate is a CA bundle or a certificate / key pair.
1. Enter the **Certificate File Path**, such as `/etc/ssl/nginx/mycert.crt`.
1. If you selected a key pair, you'll also enter the **Key File Path**, such as `/etc/ssl/nginx/mycert.key`.
1. Select **Add**. You should now be returned to the **Edit Configuration** window.
   You should now see the files you specified in the directory tree.
1. Select **Next** and then **Save and Publish**.
   You may see a message that suggests publication is in progress.
   - If the instance is offline, **Save and Publish** does not work.
1. When publication is complete, you're taken back to the **Configuration** tab. You should see the updated configuration in the window.

## See also

- [Create and manage data plane keys]({{< relref "/nginx-one/how-to/data-plane-keys/create-manage-data-plane-keys.md" >}})
- [View and edit NGINX configurations]({{< relref "/nginx-one/how-to/nginx-configs/view-edit-nginx-configurations.md" >}})
- [Manage certificates]({{< relref "/nginx-one/how-to/certificates/manage-certificates.md" >}})
