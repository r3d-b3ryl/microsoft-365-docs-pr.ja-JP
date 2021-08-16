---
title: アプリをデバイスに展開する
description: アプリをデバイスに追加および展開Microsoft マネージド デスクトップ。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント、アプリ、line-of-business アプリ、LOB アプリ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 96ad8e55dc4d7bea15da89142d42531ca46c960875b79b8579a3a5e9f0ce31d4
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53898661"
---
# <a name="deploy-apps-to-devices"></a>アプリをデバイスに展開する
アプリのオンボーディングのMicrosoft マネージド デスクトップユーザーのデバイスへのアプリの追加と展開が含まれます。 アプリ ポータルを使用Microsoft マネージド デスクトップ、アプリを追加して展開できます。 

全体的なプロセスは次のように表示されます。
1. [アプリを Microsoft マネージド デスクトップ](#1)ポータルに追加する - 既存の業務用 (LOB) アプリ、または Intune と同期した ビジネス向け Microsoft Store のアプリを指定できます。 
2. [アプリAzure Active Directory (AD)](#2)グループを作成する - これらのグループを使用してアプリの割り当てを管理します。
3. [アプリをユーザーに割り当てる](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>手順 1: アプリをポータルにMicrosoft マネージド デスクトップする
[Win32 を追加したり、MSI](#lob-apps)ベースのWindowsを追加したり、ビジネス向け Microsoft Store アプリMicrosoft マネージド デスクトップを追加したり、Microsoft マネージド デスクトップ デバイスに展開したりできます。 [](#msfb-apps)

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 Windows MSI ベースのアプリをインストールMicrosoft マネージド デスクトップ

ビジネスライン (LOB) アプリをポータルに追加Microsoft マネージド デスクトップできます。 デバイスにインストールされているアプリの要件については、「Microsoft マネージド デスクトップ要件[」を参照Microsoft マネージド デスクトップしてください](../service-description/mmd-app-requirements.md)。

この手順では、追加するアプリの種類を選択し、アプリ ソースを構成してアップロードします。 

**LOB アプリまたはアプリを WindowsポータルにMicrosoft マネージド デスクトップするには**

ポータルにサインインするかMicrosoft マネージド デスクトップ Intune にサインインして、ポータルを検索Microsoft マネージド デスクトップ。 ポータルへのサインインをMicrosoft マネージド デスクトップします。 

1.    管理者ポータルに[サインインMicrosoft マネージド デスクトップします](https://aka.ms/mmdportal)。 
2.    [インベントリ **] で**、[アプリ] **を選択します**。
3.    [アプリ] ワークロードで、[追加] を **選択します**。
4.    [**アプリの追加]** で **、[Line-of-business アプリ**] または [アプリWindows **(Win32) を選択します**。
    - [Line-of-business app] を選択した場合は、「Windows **line-of-business** アプリを [Microsoft Intune](/intune/lob-apps-windows)に追加して構成する」を参照してください。
    - アプリ **(Win32) Windows選択** した場合は [、「Win32](/intune/apps-win32-app-management)アプリの管理」を参照して、アプリの追加と構成Windowsしてください。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>ビジネス向け Microsoft Storeアプリ
アプリにサインアップしていないビジネス向け Microsoft Store、アプリを購入するときにサインアップできます。 アプリを作成した後、アプリとアプリを同期Microsoft マネージド デスクトップ。 

**アプリをアプリから購入ビジネス向け Microsoft Store**

1. 管理者アカウントで[ビジネス向け Microsoft Store](https://businessstore.microsoft.com)サインインビジネス向け Microsoft Storeします。
2. [自分 **のグループのショップ] を選択します**。
3. 検索を使用して、目的のアプリを検索し、アプリを選択します。
4. 製品の詳細で、[アプリの取得 **] を選択します**。 Microsoft Store、組織の **製品にアプリ** を追加します。

**Intune とデバイス間の同期を強制的に行ビジネス向け Microsoft Store**
1. Microsoft エンドポイント マネージャー管理センター
2. [**テナント管理**  >  **コネクタとトークン] を**  >  **選択** ビジネス向け Microsoft Store。
3. [**同期]** を選択して、アプリから購入したアプリを Intune Microsoft Store取得します。

**Intune とデバイス間の同期がアクティブビジネス向け Microsoft Storeするには**
1. 管理者アカウントで[ビジネス向け Microsoft Store](https://businessstore.microsoft.com)サインインビジネス向け Microsoft Storeします。
2. [管理 **] を選択します**。
3. [配布 **設定] を** 選択し、[配布] を **選択します**。
4. [ **管理ツール]** で、Intune が一覧に表示され、状態が [アクティブ] である必要 **があります**。  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>手順 2: Azure ADグループを作成する

アプリごとに 3 つの Azure ADグループを作成します。 次の表に、必要なグループ (利用可能、必須、アンインストール) の概要を示します。 

アプリの割り当ての種類 |    グループの使用    | Azure の名前AD例
--- | --- | ---
Available |  アプリは、アプリまたは web サイトポータル サイト利用できます。 | MMD – *アプリ名* – 使用可能
必須 |  アプリは、選択したグループ内のデバイスにインストールされます。 | MMD – *アプリ名* – 必須
アンインストール |  アプリは、選択したグループ内のデバイスからアンインストールされます。 | MMD – *アプリ名* – アンインストール

これらのグループにユーザーを追加して、アプリを利用可能にするか、アプリをインストールするか、アプリをデバイスから削除Microsoft マネージド デスクトップします。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>手順 3: ユーザーにアプリを割り当てる

**アプリをユーザーに割り当てるには**

1. 管理者ポータルに[サインインMicrosoft マネージド デスクトップします](https://aka.ms/mmdportal)。
2. [管理デスクトップ] ウィンドウで、[アプリ] を **選択します**。
3. [アプリ] ワークロードで、ユーザーを割り当てるアプリを選択し、[ユーザー グループの割り当て **] を選択します**。
4. 特定のアプリで、割り当ての種類 (利用可能、必須、アンインストール) を選択し、適切なグループを割り当てる。
5. [アプリの割り当て] ウィンドウで **、[OK] を選択します**。


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>データの使用を開始するMicrosoft マネージド デスクトップ

1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)
2. [条件付きアクセスを調整する](conditional-access.md)
3. [ライセンスを割り当てる](assign-licenses.md)
4. [Intune 会社ポータルを展開する](company-portal.md)
5. [Enterprise State Roaming を有効にする](enterprise-state-roaming.md)
6. [デバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. アプリの展開 (このトピック)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->