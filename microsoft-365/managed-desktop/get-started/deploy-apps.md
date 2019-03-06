---
title: Microsoft マネージドデスクトップデバイス用のアプリを展開する
description: Microsoft マネージドデスクトップデバイスへのアプリの追加および展開に関する情報。
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント、アプリ、基幹業務アプリ、LOB アプリ
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: febb3198c434e638f83c412a3f8a3b688d9f5bd1
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414172"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>アプリを Microsoft マネージドデスクトップデバイスに展開する
Microsoft Managed Desktop へのオンボードの一部には、ユーザーのデバイスへのアプリの追加と展開が含まれます。 Microsoft マネージドデスクトップポータルを使用している場合は、アプリを追加して展開することができます。 

全体的なプロセスは次のようになります。
1. [microsoft マネージドデスクトップポータルへのアプリの追加](#1)-既存の基幹業務 (LOB) アプリ、または Intune と同期したビジネス向け Microsoft Store のアプリにすることができます。 
2. [アプリの割り当て用に Azure Active Directory (AD) グループを作成](#2)する-これらのグループを使用して、アプリの割り当てを管理します。
3. [ユーザーにアプリを割り当てる](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>手順 1: Microsoft マネージドデスクトップポータルにアプリを追加する
microsoft マネージドデスクトップには、 [Win32、Windows MSI ベースのアプリ](#lob-apps)、または[microsoft Store for Business アプリ](#msfb-apps)を追加し、それを microsoft マネージドデスクトップデバイスに展開することができます。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップへの Win32 または Windows MSI ベースのアプリ

基幹業務 (LOB) アプリを Microsoft マネージドデスクトップポータルに追加できます。 microsoft マネージドデスクトップデバイスにインストールされているアプリの要件の詳細については、「 [microsoft managed desktop app の要件](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)」を参照してください。

この手順では、追加するアプリの種類を選択してから、アプリソースを構成およびアップロードします。 

**LOB アプリまたは Windows アプリを Microsoft マネージドデスクトップポータルに追加するには**

microsoft マネージドデスクトップポータルにサインインするか、Intune にサインインして、microsoft managed desktop を検索することができます。 Microsoft マネージドデスクトップポータルへのサインインを表示します。 

1.  [Microsoft Managed Desktop 管理ポータル](http://aka.ms/mmdportal)にサインインします。 
2.  [**インベントリ**] で、[**アプリ**] を選択します。
3.  [アプリのワークロード] で、[**追加**] を選択します。
4.  [**アプリの追加**] で、[**基幹業務アプリ**] または [ **Windows アプリ (Win32)-プレビュー**] を選択します。
    - 基幹**業務アプリ**を選択した場合は、基幹業務アプリを追加して構成する手順については、「 [Windows の基幹業務アプリを Microsoft Intune に追加](https://docs.microsoft.com/intune/lob-apps-windows)する」を参照してください。
    - **windows アプリ (Win32) プレビュー**を選択した場合は、「 [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) 」を参照してください。 windows アプリを追加および構成する方法について説明します。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>ビジネス向け Microsoft Store アプリ
Microsoft Store for Business にサインアップしていない場合は、アプリの購入時にサインアップできます。 アプリを用意したら、それらを Microsoft マネージドデスクトップと同期することができます。 

**ビジネス向け Microsoft Store からアプリを購入するには**

1. business 管理者アカウントの microsoft store を使用して、 [microsoft store for business](https://businessstore.microsoft.com)にサインインします。
2. [**自分のグループのショッピング**] を選択します。
3. 検索を使用して目的のアプリを見つけ、アプリを選択します。
4. [製品の詳細] で、[**アプリの取得**] を選択します。 Microsoft Store は、組織のためにアプリを**Products & サービス**に追加します。

**ビジネス向けに Intune と Microsoft Store 間の同期を強制するには**
1. テナントのために Intune 管理者またはグローバル管理者として[Azure Portal](https://portal.azure.com/)にサインインします。
2. [**すべてのサービス > Intune**] を選択します。 Intune は、[監視 + 管理] セクションにあります。
3. [Intune] ウィンドウで、[**クライアントアプリ**] を選択し、[**ビジネス向け Microsoft Store**] を選択します。
4. [**有効**] を選択して、Microsoft Store for Business アプリを Intune と同期します。
    - まだ登録していない場合は、Microsoft Store for Business アカウントを Intune に関連付けます。
    - Intune コンソールに Microsoft Store for Business のアプリが表示される言語を選択します
    - Microsoft Store for Business アプリを Intune と同期するには、[**同期**] を選択します。
    - Microsoft Store for Business と Intune の間の同期がアクティブであることを確認します (次の手順)。 

**Intune と Microsoft Store for Business の同期がアクティブであることを確認するには**
1. business 管理者アカウントの microsoft store を使用して、 [microsoft store for business](https://businessstore.microsoft.com)にサインインします。
2. [**管理**] を選択します。
3. [**設定**] を選択し、[**配布**] を選択します。
4. [**管理ツール**] で、Intune が表示され、状態が [**アクティブ**] になっていることを確認します。  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>手順 2: Azure AD グループを作成する

アプリごとに3つの Azure AD グループを作成します。 次の表に、必要なグループ (利用可能、必要、およびアンインストール) の概要を示します。 

アプリの割り当ての種類 |   グループの使用   | Azure AD 名の例
--- | --- | ---
Available |  アプリは、会社のポータルアプリまたは web サイトから入手できます。 | MMD –*アプリ名*–利用可能
必須 |  アプリは、選択したグループのデバイスにインストールされます。 | MMD –*アプリ名*–必須
Uninstall |  なアプリは、選択したグループのデバイスからアンインストールされます。 | MMD –*アプリ名*–アンインストール

これらのグループにユーザーを追加して、アプリを利用できるようにするか、アプリをインストールするか、Microsoft マネージドデスクトップデバイスからアプリを削除します。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>手順 3: ユーザーにアプリを割り当てる

**アプリをユーザーに割り当てるには**

1. [Microsoft Managed Desktop 管理ポータル](http://aka.ms/mmdportal)にサインインします。
2. [管理されたデスクトップ] ウィンドウで、[**アプリ**] を選択します。
3. [アプリのワークロード] で、ユーザーの割り当て先となるアプリを選択し、[**ユーザーグループの割り当て**] を選択します。
4. 特定のアプリについて、割り当ての種類 (利用可能、必須、アンインストール) を選択し、適切なグループを割り当てます。
5. [アプリの割り当て] ウィンドウで、[ **OK]** を選択します。

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