---
title: 'Tutorial: Azure Active Directory integration with RedBrick Health | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and RedBrick Health.
services: active-directory
documentationCenter: na
author: jeevansd
manager: mtillman
ms.reviewer: barbkess

ms.assetid: 26290c65-9aa3-42ab-8ba5-901b14dc8e73
ms.service: Azure-Active-Directory
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: tutorial
ms.date: 1/3/2019
ms.author: jeedes

---
# Tutorial: Azure Active Directory integration with RedBrick Health

In this tutorial, you learn how to integrate RedBrick Health with Azure Active Directory (Azure AD).
Integrating RedBrick Health with Azure AD provides you with the following benefits:

* You can control in Azure AD who has access to RedBrick Health.
* You can enable your users to be automatically signed-in to RedBrick Health (Single Sign-On) with their Azure AD accounts.
* You can manage your accounts in one central location - the Azure portal.

If you want to know more details about SaaS app integration with Azure AD, see [What is application access and single sign-on with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis).
If you don't have an Azure subscription, [create a free account](https://azure.microsoft.com/free/) before you begin.

## Prerequisites

To configure Azure AD integration with RedBrick Health, you need the following items:

* An Azure AD subscription. If you don't have an Azure AD environment, you can get one-month trial [here](https://azure.microsoft.com/pricing/free-trial/)
* RedBrick Health single sign-on enabled subscription

## Scenario description

In this tutorial, you configure and test Azure AD single sign-on in a test environment.


* RedBrick Health supports **IDP** initiated SSO




## Adding RedBrick Health from the gallery

To configure the integration of RedBrick Health into Azure AD, you need to add RedBrick Health from the gallery to your list of managed SaaS apps.

**To add RedBrick Health from the gallery, perform the following steps:**

1. In the **[Azure portal](https://portal.azure.com)**, on the left navigation panel, click **Azure Active Directory** icon.

	![The Azure Active Directory button](common/select-azuread.png)

2. Navigate to **Enterprise Applications** and then select the **All Applications** option.

	![The Enterprise applications blade](common/enterprise-applications.png)

3. To add new application, click **New application** button on the top of dialog.

	![The New application button](common/add-new-app.png)

4. In the search box, type **RedBrick Health**, select **RedBrick Health** from result panel then click **Add** button to add the application.

	 ![RedBrick Health in the results list](common/search-new-app.png)

## Configure and test Azure AD single sign-on

In this section, you configure and test Azure AD single sign-on with RedBrick Health based on a test user called **Britta Simon**.
For single sign-on to work, a link relationship between an Azure AD user and the related user in RedBrick Health needs to be established.

To configure and test Azure AD single sign-on with RedBrick Health, you need to complete the following building blocks:

1. **[Configure Azure AD Single Sign-On](#configure-azure-ad-single-sign-on)** - to enable your users to use this feature.
2. **[Configure RedBrick Health Single Sign-On](#configure-redbrick-health-single-sign-on)** - to configure the Single Sign-On settings on application side.
3. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with Britta Simon.
4. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable Britta Simon to use Azure AD single sign-on.
5. **[Create RedBrick Health test user](#create-redbrick-health-test-user)** - to have a counterpart of Britta Simon in RedBrick Health that is linked to the Azure AD representation of user.
6. **[Test single sign-on](#test-single-sign-on)** - to verify whether the configuration works.

### Configure Azure AD single sign-on

In this section, you enable Azure AD single sign-on in the Azure portal.

To configure Azure AD single sign-on with RedBrick Health, perform the following steps:

1. In the [Azure portal](https://portal.azure.com/), on the **RedBrick Health** application integration page, select **Single sign-on**.

    ![Configure single sign-on link](common/select-sso.png)

2. On the **Select a Single sign-on method** dialog, select **SAML/WS-Fed** mode to enable single sign-on.

    ![Single sign-on select mode](common/select-saml-option.png)

3. On the **Set up Single Sign-On with SAML** page, click **Edit** icon to open **Basic SAML Configuration** dialog.

	![Edit Basic SAML Configuration](common/edit-urls.png)

4. On the **Basic SAML Configuration** section, perform the following steps:

    ![RedBrick Health Domain and URLs single sign-on information](common/idp-relay.png)

    a. In the **Identifier** text box, type a URL:
    `https://www.redbrickhealth.com`

    b. In the **Reply URL** text box, type a URL:
    `https://sso-intg.redbrickhealth.com/sp/ACS.saml2`

	For Production Environment: `https://sso.redbrickhealth.com/sp/ACS.saml2`

    c. Click **set additional URLs**.

    d. In the **Relay State** text box, type a URL using the following pattern:
    `https://api-sso2.redbricktest.com/identity/sso/nbound?target=https://vanity9-sso2.redbrickdev.com/portal&connection=<companyname>conn1`

	> [!NOTE]
	> Relay State value is not real. Update this value with the actual Relay State. Contact [RedBrick Health Client support team](https://home.redbrickhealth.com/contact/) to get this value. You can also refer to the patterns shown in the **Basic SAML Configuration** section in the Azure portal.

5. RedBrick Health application expects the SAML assertions in a specific format. Configure the following claims for this application. You can manage the values of these attributes from the **User Attributes** section on application integration page. On the **Set up Single Sign-On with SAML** page, click **Edit** button to open **User Attributes** dialog.

	![image](common/edit-attribute.png)

6. In the **User Claims** section on the **User Attributes** dialog, configure SAML token attribute as shown in the image above and perform the following steps:

	| Name | Source Attribute|
	| ---------------| --------------- | --------- |
	| principal name | ********** |
	| client id | ********** |
	| participant id | ********** |

	> [!NOTE]
	> These values are for reference purpose only. You need to define the attributes as per your organization's requirement. Please contact [RedBrick Health support team](https://home.redbrickhealth.com/contact/) to get more info about the required claims.

	a. Click **Add new claim** to open the **Manage user claims** dialog.

	![image](common/new-save-attribute.png)

	![image](common/new-attribute-details.png)

	b. In the **Name** textbox, type the attribute name shown for that row.

	c. Leave the **Namespace** blank.

	d. Select Source as **Attribute**.

	e. From the **Source attribute** list, type the attribute value shown for that row.

	f. Click **Ok**

	g. Click **Save**.

7. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, click **Download** to download the **Certificate (Base64)** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/certificatebase64.png)

8. On the **Set up RedBrick Health** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

	a. Login URL

	b. Azure Ad Identifier

	c. Logout URL

### Configure RedBrick Health Single Sign-On

To configure single sign-on on **RedBrick Health** side, you need to send the downloaded **Certificate (Base64)** and appropriate copied URLs from Azure portal to [RedBrick Health support team](https://home.redbrickhealth.com/contact/). They set this setting to have the SAML SSO connection set properly on both sides.

### Create an Azure AD test user

The objective of this section is to create a test user in the Azure portal called Britta Simon.

1. In the Azure portal, in the left pane, select **Azure Active Directory**, select **Users**, and then select **All users**.

    ![The "Users and groups" and "All users" links](common/users.png)

2. Select **New user** at the top of the screen.

    ![New user Button](common/new-user.png)

3. In the User properties, perform the following steps.

    ![The User dialog box](common/user-properties.png)

    a. In the **Name** field enter **BrittaSimon**.
  
    b. In the **User name** field type **brittasimon@yourcompanydomain.extension**  
    For example, BrittaSimon@contoso.com

    c. Select **Show password** check box, and then write down the value that's displayed in the Password box.

    d. Click **Create**.

### Assign the Azure AD test user

In this section, you enable Britta Simon to use Azure single sign-on by granting access to RedBrick Health.

1. In the Azure portal, select **Enterprise Applications**, select **All applications**, then select **RedBrick Health**.

	![Enterprise applications blade](common/enterprise-applications.png)

2. In the applications list, select **RedBrick Health**.

	![The RedBrick Health link in the Applications list](common/all-applications.png)

3. In the menu on the left, select **Users and groups**.

    ![The "Users and groups" link](common/users-groups-blade.png)

4. Click the **Add user** button, then select **Users and groups** in the **Add Assignment** dialog.

    ![The Add Assignment pane](common/add-assign-user.png)

5. In the **Users and groups** dialog select **Britta Simon** in the Users list, then click the **Select** button at the bottom of the screen.

6. If you are expecting any role value in the SAML assertion then in the **Select Role** dialog select the appropriate role for the user from the list, then click the **Select** button at the bottom of the screen.

7. In the **Add Assignment** dialog click the **Assign** button.

### Create RedBrick Health test user

In this section, you create a user called Britta Simon in RedBrick Health. Work with [RedBrick Health support team](https://home.redbrickhealth.com/contact/) to add the users in the RedBrick Health platform. Users must be created and activated before you use single sign-on.

### Test single sign-on

In this section, you test your Azure AD single sign-on configuration using the Access Panel.

When you click the RedBrick Health tile in the Access Panel, you should be automatically signed in to the RedBrick Health for which you set up SSO. For more information about the Access Panel, see [Introduction to the Access Panel](https://docs.microsoft.com/azure/active-directory/active-directory-saas-access-panel-introduction).

## Additional Resources

- [ List of Tutorials on How to Integrate SaaS Apps with Azure Active Directory ](https://docs.microsoft.com/azure/active-directory/active-directory-saas-tutorial-list)

- [What is application access and single sign-on with Azure Active Directory? ](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)

- [What is conditional access in Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)

