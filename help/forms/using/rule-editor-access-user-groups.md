---
title: Grant rule editor access to select user groups
seo-title: Grant rule editor access to select user groups
description: Grant restricted access to rule editor to select user groups.
seo-description: Grant restricted access to rule editor to select user groups.
uuid: 3d982858-b2b5-4370-a9d7-5a95842a7897
content-type: reference
topic-tags: adaptive_forms, develop
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 6bd58e37-085e-4057-8200-1404d54f41cc
feature: Adaptive Forms
exl-id: 5e2960f2-b172-48a7-bba3-4561a5f9c7bc
---
# Grant rule editor access to select user groups {#grant-rule-editor-access-to-select-user-groups}

## Overview {#overview}

You may have different types of users with varied skills that work with Adaptive Forms. While expert users may have the right knowledge to work with scripts and complex rules, there may be basic-level users who need to work only with the layout and basic properties of adaptive forms.

AEM Forms allows you to limit rule editor access to users based on their role or function. In the Adaptive Forms Configuration Service settings, you can specify the [user groups](/help/sites-administering/security.md) that can view and access rule editor.

## Specify user groups that can access rule editor {#specify-user-groups-that-can-access-rule-editor}

1. Log in to AEM Forms as an administrator.
1. In the author instance, click ![adobeexperiencemanager](assets/adobeexperiencemanager.png)Adobe Experience Manager &gt; Tools ![hammer](assets/hammer.png) &gt; Operations &gt; Web Console. The Web Console opens in a new window.

   ![1](assets/1.png)

1. In Web Console Window, locate and click **[!UICONTROL Adaptive Form and Interactive Communication Web Channel Configuration]**. **[!UICONTROL Adaptive Form and Interactive Communication Web Channel Configuration]** dialog appears. Do not change any value and click **[!UICONTROL Save]**.

   It creates a file /apps/system/config/com.adobe.aemds.guide.service.impl.AdaptiveFormConfigurationServiceImpl.config in CRX-repository.

1. Log in to CRXDE as an administrator. Open file /apps/system/config/com.adobe.aemds.guide.service.impl.AdaptiveFormConfigurationServiceImpl.config for editing.
1. Use the following property to specify the name of a group that can access rule editor (For example, RuleEditorsUserGroup) and click **Save All**.

   `af.ruleeditor.custom.groups=["RuleEditorsUserGroup"]`

   To enable access for mutiple groups, specify a list of comma seperated values:

   `af.ruleeditor.custom.groups=["RuleEditorsUserGroup", "PermittedUserGroup"]`

   ![create-user](assets/create-user.png)

   Now, when a user that is not a part of the specified user group (here RuleEditorsUserGroup) taps a field, the Edit Rule icon ( ![edit-rules1](assets/edit-rules1.png)) is not available for her in the components toolbar:

   ![componentstoolbarwithre](assets/componentstoolbarwithre.png)

   Components toolbar as visible to a user with rule editor access

   ![componentstoolbarwithoutre](assets/componentstoolbarwithoutre.png)

   Components toolbar as visible to a user without rule editor access

   For instructions on adding users to groups, see [User Administration and Security](/help/sites-administering/security.md).
