---
title: Microsoft 管理デスクトップ デバイス用のアプリケーションを展開します。
description: 追加および管理されたデスクトップのマイクロソフトのデバイスにアプリケーションを展開するための情報です。
keywords: 管理されたデスクトップの Microsoft、Microsoft 365、サービス、ドキュメント、アプリケーション、基幹業務アプリケーション、LOB アプリケーション
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341612"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Microsoft 管理されたデスクトップのデバイスにアプリケーションを配備します。
追加して、ユーザーのデバイスにアプリケーションを展開する、管理されたデスクトップのマイクロソフトに契約時の一部が含まれます。管理されたデスクトップの Microsoft のポータルを使用して後、は、追加し、アプリケーションを展開します。 

プロセス全体は、次のようになります。
1. [管理されたデスクトップの Microsoft のポータルに追加のアプリケーション](#1)のこのことがでく既存の基幹業務 (LOB) アプリケーション、または Intune と同期しているビジネスのマイクロソフト ストアからのアプリです。 
2. [アプリケーションの割り当てのグループを作成 Azure Active Directory (AD)](#2) - アプリケーションの割り当てを管理するためにこれらのグループを使用します。
3. [アプリケーションをユーザーに割り当てる](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>手順 1: 管理されたデスクトップの Microsoft のポータルにアプリケーションを追加します。
Microsoft 管理されたデスクトップでは、 [Win32 または Windows MSI ベースのアプリケーション](#lob-apps)、または[ビジネス アプリケーションのマイクロソフト ストア](#msfb-apps)に追加し、管理されたデスクトップのマイクロソフトのデバイスに配置できます。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 や Windows MSI ベースのアプリケーションを Microsoft デスクトップの管理

管理されたデスクトップの Microsoft のポータルには、基幹業務 (LOB) アプリケーションを追加できます。Microsoft 管理デスクトップ デバイスにインストールされているアプリケーションの要件については、[マイクロソフトの管理されたデスクトップ アプリケーションの要件](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)を参照してください。

この手順では、どのようなアプリケーションの追加、および構成し、アプリケーションのソースをアップロードするを選択します。 

**管理されたデスクトップの Microsoft のポータルに、LOB アプリケーションや Windows アプリケーションを追加するのには**

管理されたデスクトップの Microsoft のポータルにサインインまたは Intune にサインインし、Microsoft の管理されたデスクトップを検索できます。管理されたデスクトップの Microsoft のポータルへのサインインをご紹介します。 

1.  [マイクロソフト デスクトップ管理の管理ポータル](http://aka.ms/mmdportal)にサインインします。 
2.  **在庫**の下には、**アプリケーション**を選択します。
3.  アプリケーション ・ ワークロードの**追加**を] を選択します。
4.  **追加のアプリケーション**では、**基幹業務アプリケーション**または**Windows アプリケーション (Win32) のプレビュー**を選択します。
    - **基幹業務アプリケーション**を選択した場合の追加、および基幹業務アプリケーションを構成する方法について[Microsoft Intune に Windows の基幹業務アプリケーションの追加](https://docs.microsoft.com/intune/lob-apps-windows)を参照してください。
    - **Windows アプリケーション (Win32) のプレビュー**を選択した場合を追加して、Windows アプリケーションを構成する手順の[Win32 アプリケーションの管理](https://docs.microsoft.com/intune/apps-win32-app-management)を参照してください。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>ビジネス アプリケーション用の Microsoft ストア
ビジネス向けのマイクロソフト ストアにサインアップしていない場合は、アプリを買いに行くとき署名できます。アプリがある場合は後、は、Microsoft の管理されたデスクトップと同期できます。 

**ビジネスのマイクロソフト ストアからアプリケーションを購入するには**

1. ビジネス管理者のアカウントに、マイクロソフトのストアを使用して[ビジネスのためのマイクロソフト ストア](https://businessstore.microsoft.com)にサインインします。
2. **ショップ**を選択します。
3. 検索を使用して、必要なアプリケーションを検索して、アプリケーションを選択します。
4. 製品詳細については、**アプリケーションを取得する**を選択します。マイクロソフト ストアでは、組織の**製品の & サービス**にアプリケーションを追加します。

**Intune とビジネス向けのマイクロソフト ストア間で同期を強制するには**
1. テナントの Intune 管理者またはグローバル管理者として[Azure ポータル](https://portal.azure.com/)にサインインします。
2. **サービス _gt Intune のすべて**を選択します。Intune は、監視と管理のセクションです。
3. Intune ウィンドウは、**クライアント アプリケーション**を選択し、**ビジネス向けのマイクロソフト ストア**を選択します。
4. Intune でのビジネス アプリケーションで、Microsoft ストアを同期する**を有効にする**を選択します。
    - いない場合、記号と関連付け、Microsoft の格納 Intune とビジネス アカウント
    - Intune コンソールにビジネス向けのマイクロソフト ストアからのアプリが表示されます言語を選択します。
    - Intune でのビジネス アプリケーションで、Microsoft ストアを同期する**同期**を選択します。
    - ビジネス向けのマイクロソフト ストアと Intune の間で同期がアクティブであることを確認 (次の手順)。 

**Intune とビジネス向けのマイクロソフト ストア間で同期がアクティブであることを確認するのには**
1. ビジネス管理者のアカウントに、マイクロソフトのストアを使用して[ビジネスのためのマイクロソフト ストア](https://businessstore.microsoft.com)にサインインします。
2. **管理**を選択します。
3. **設定**を選択し、**整列**を選択します。
4. [**管理ツール**] には、Intune が表示されていることと、状態が**アクティブ**であるを確認します。  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Azure AD グループを作成する手順 2。

各アプリケーションの 3 つの Azure AD グループを作成します。この表は、グループする必要があります (使用可能な必要な場合、およびアンインストール) します。 

アプリケーションの割り当ての種類 |   グループの使用   | Azure AD の例の名前
--- | --- | ---
使用可能 |  アプリケーションは企業ポータル アプリケーションまたは web サイトから利用可能になります。 | MMD:*アプリケーション名*: 利用可能
必須 |  アプリケーションは、選択したグループ内のデバイスにインストールされます。 | MMD:*アプリケーション名*: 必須
[アンインストール] |  単位のアプリケーションは、選択したグループ内のデバイスからアンインストールされます。 | MMD:*アプリケーション名*: アンインストール

アプリケーションの利用を行う、アプリケーションをインストールするか、管理されたデスクトップの Microsoft デバイスからアプリケーションを削除するこれらのグループにユーザーを追加します。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>手順 3: アプリケーションをユーザーに割り当てる

**ユーザーにアプリケーションを割り当てるには**

1. [マイクロソフト デスクトップ管理の管理ポータル](http://aka.ms/mmdportal)にサインインします。
2. デスクトップの管理ウィンドウで、**アプリケーション**を選択します。
3. アプリケーションの作業負荷でアプリケーションをユーザーに割り当てるし、**ユーザー グループの割り当て**を選択するを選択します。
4. 特定のアプリケーションでは、割り当ての種類 (利用可能な必要な場合、アンインストール) を選択し、適切なグループを割り当てます。
5. 割り当てるアプリケーション ウィンドウで、 **[ok]** を選択します。

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->