---

copyright:
  years: 2017, 2024
lastupdated: "2024-08-02"

subcollection: hardware-firewall-shared

---

{{site.data.keyword.attribute-definition-list}}

# Managing permissions
{: #managing-permissions}

To view and manage your hardware firewalls, you need the correct permissions. After your account administrator grants your user account permissions and access, you can view your hardware firewall details by using the {{site.data.keyword.cloud}} console, or by using the {{site.data.keyword.slapi_short}}. The information or actions that you see depend on your permissions.
{: shortdesc}

The following permissions are required for viewing and managing various parts of your hardware firewalls:

* **Manage firewalls** - Allows you to view your list of firewalls. It also allows you to view and manage the details of a specific firewall.
* **View hardware details** - Allows you to view your list of hardware firewalls on bare metal servers. It also allows you to view and manage the details of a specific hardware firewall on a bare metal server.
* **View virtual server details** - Allows you to view your list of firewalls on virtual servers. It also allows you to view and manage the details of a specific hardware firewall on a virtual server.
* **Manage firewall rules** - Allows you to manage the rules of a specific hardware firewall.
* **Cancel services** - Allows you to cancel a firewall.

## Adding permissions for your users
{: #adding-permissions-for-your-users}

If you are the account administrator and you want to grant a user permission to view and manage gateway appliance details, complete the following steps.

1. Log in to the [Access (IAM)](/iam/users){: external} page in the {{site.data.keyword.cloud}} console.
2. Select **View: My classic infrastructure users**.
3. Select a user, click the **Classic infrastructure** tab, then click the **Permissions** tab.
4. Expand the **Devices** category and select **Manage firewalls**.
5. Expand the **Devices** category and select **View hardware details**.
6. Expand the **Devices** category and select **View virtual server details**.
7. Expand the **Devices** category and select **Manage firewall rules**.
8. Expand the **Account** category and select **Cancel services**.
9. Click **Apply**.

## Next steps
{: #next-steps}

User permissions are updated immediately after the changes are submitted. If permissions are granted, the user can view or interact with the selected features. If permissions are removed, the user can no longer view or interact with the selected features. Permissions can be updated again at any time.
