---
title: Manage the enhanced Active Conversation settings | MicrosoftDocs 
description: Manage the enhanced Active Conversation settings
author: gandhamm 
ms.author: mgandham
ms.reviewer: neeranelli
ms.service: dynamics-365 
ms.topic: how-to 
ms.date: 05/03/2023 
ms.custom: bap-template 
---

# Manage enhanced Active Conversation settings

The enhanced Active Conversation experience enables you to customize the **Active Conversation** form to display customer and case details that are relevant to your business. When you enable this option, the **Customer 360**, **Case details**, and **Recent cases** components are available on the **Active Conversation** form by default. You can customize these components further in Power Apps.

- **Customer details**: Use the **Customer 360** component in **Account** > **Account form for Conversation Customer Card** form or **Contact** > **Contact form for Conversation Customer Card** to customize the details displayed on **Customer details**.
- **Case details**: Use the **Customer 360** component in **Case** > **Case for Customer Card** form to customize the details displayed on **Case details**. 
- You can also set the required view to display case details in the **Issue Snapshot**. By default, the **Default view** is set to **Case Lookup View**.

 More information: [Configure components to display customer details and recent records](add-display-components-to-case-form.md).

## Enable enhanced Active Conversation

1. In Customer Service admin center, go to **Customer Settings**.
1. Select **Manage** for **Enhanced conversation form** in **Form Settings**.
1. Set the **Enhanced Active conversation form** toggle to yes in **Enhanced conversation form**.
2. Select **Configure** to further customize the enhanced Active Conversation form. More information: [Create and customize a model-driven app form](/power-apps/maker/model-driven-apps/create-and-edit-a-model-driven-form).

## Display the form selector on Active Conversation form

By default, the enhanced **Active Conversation** form doesn't display the form selector to switch between open and closed conversations. To allow your users to toggle between open and closed conversations, do the following steps:

1. In [Power Apps](https://make.powerapps.com/), add the **Unhide Conversation form selector** setting definition. More information: [Add an existing setting definition](/power-apps/maker/data-platform/create-edit-configure-settings#adding-an-existing-setting-definition)
1.  In the **Edit Unhide Conversation form selector**, set the **Setting environment value** option to **Yes**. More information: [Update a setting definition](/power-apps/maker/data-platform/create-edit-configure-settings#updating-a-setting-definition)
1. Optionally, in the **Setting app values** section, for a required app, you can set the value to **Yes** in the **New app value**. The tab set at the application level overrides the environment level setting.
1. Save and publish your customizations.
     
    :::image type="content" source="media/powerapps-unhide-selector.png" alt-text="View the unhide selector" lightbox="media/powerapps-unhide-selector-mini.png"::: 


## Customize recent cases

If you set the **Enhanced Active conversation form** toggle to **Yes**, the enhanced **Recent cases** control is available on the **Active Conversation** form, out of the box. If you've set the default view to a custom view in the legacy recent cases control, when you switch to the enhanced experience, your custom views aren't set as the default view automatically. You must set the default view to your required custom view in Power Apps.

To add your custom view as the default view and customize the form further, perform the following steps:

1. In [Power Apps](https://make.preview.powerapps.com/), select the environment that contains your solution.
1. Select **Tables**, select **Conversation**, and then select the **Active Conversation** form.
1. Select **Recent cases** on the **Form** area.
1. Do the following actions in **Properties**: 
   - Specify the **Table**. The card displays records from this table.
   - Select the **Default view** to your required custom view.


## Disable enhanced customer details, case details, or recent cases

You can choose to display the default **Customer profile**, **Issue snapshot**, or **Recent cases** cards on the enhanced **Active Conversation** form even when **Enhanced active conversation form** is enabled.

The following options are available out of the box in Power Apps:

|Option   | Description   |
|----------|-----------|
|Disable Customer 360 card for Open Conversation | Set this option to **Yes** to display the default **Customer profile** card.  |
|Disable Linked Case card for Open Conversation | Set this option to **Yes**, to display the default **Issue Snapshot** card.   |
|Disable the recent cases control for Open conversation | Set this option to **Yes**, to display the default **Recent cases** card.   |

Perform the following steps to revert to the required default experience:

1. In [Power Apps](https://make.powerapps.com/), select the environment that contains your solution.
2. Select **Solutions**, and then select the required solution.
4. Select **Add Existing** > **More** > **Setting**.
1. On the **Add existing Setting Definition** pane, select the required option.
1. Select **Add**.
1.  Go to **Add Existing** > **App** > **Model-driven app**> **Add existing model-driven apps** pane.
1. On the edit pane for the required option, set **Setting environment value**  to **Yes**.
1. Optionally, select **New app value** for the app. For a specified app, the value set at the application level overrides the environment level setting.
1. Select **Publish All Customizations**.


### See also

[View customer information on Active Conversation form](oc-customer-summary.md) <br>
[Get started with Customer Service workspace](csw-overview.md)
