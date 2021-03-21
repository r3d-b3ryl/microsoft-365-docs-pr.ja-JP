---
title: アプリをデバイスに展開する
description: Microsoft Managed Desktop デバイスへのアプリの追加と展開に関する情報。
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentation, apps, line-of-business apps, LOB apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922028"
---
# <a name="deploy-apps-to-devices"></a>アプリをデバイスに展開する
Microsoft Managed Desktop へのオンボードの一部には、ユーザーのデバイスへのアプリの追加と展開が含まれます。 Microsoft Managed Desktop ポータルを使用すると、アプリを追加して展開できます。 

全体的なプロセスは次のように表示されます。
1. [Microsoft Managed Desktop](#1) ポータルにアプリを追加する - 既存の業務用 (LOB) アプリ、または Intune と同期した Microsoft Store for Business のアプリを使用できます。 
2. [アプリの割り](#2) 当AD Azure Active Directory (AD) グループを作成する - これらのグループを使用してアプリの割り当てを管理します。
3. [アプリをユーザーに割り当てる](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>手順 1: Microsoft Managed Desktop ポータルにアプリを追加する
[Win32、または Windows MSI](#lob-apps)ベースのアプリ、または[Microsoft Store for Business](#msfb-apps)アプリを Microsoft Managed Desktop に追加し、Microsoft マネージ デスクトップ デバイスに展開できます。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Microsoft マネージ デスクトップへの Win32 または Windows MSI ベースのアプリ

ビジネスライン (LOB) アプリを Microsoft マネージ デスクトップ ポータルに追加できます。 Microsoft Managed Desktop デバイスにインストールされているアプリの要件については [、「Microsoft Managed Desktop](../service-description/mmd-app-requirements.md)アプリの要件」を参照してください。

この手順では、追加するアプリの種類を選択し、アプリ ソースを構成してアップロードします。 

**LOB アプリまたは Windows アプリを Microsoft Managed Desktop ポータルに追加するには**

Microsoft Managed Desktop ポータルにサインインするか、Intune にサインインしてから Microsoft Managed Desktop を検索できます。 Microsoft Managed Desktop ポータルへのサインインが表示されます。 

1.    [Microsoft Managed Desktop Admin ポータルにサインインします](https://aka.ms/mmdportal)。 
2.    [インベントリ **] で**、[アプリ] **を選択します**。
3.    [アプリ] ワークロードで、[追加] を **選択します**。
4.    [ **アプリの追加]** で **、[Line-of-business アプリ** ] または **[Windows アプリ (Win32) ] を選択します**。
    - **[Line-of-business** アプリ] を選択した場合は、「Microsoft Intune に [Windows line-of-business](/intune/lob-apps-windows)アプリを追加する」を参照してください。
    - Windows アプリ **(Win32)** を選択した場合は、「Windows アプリの追加と構成」の手順については [、「Win32](/intune/apps-win32-app-management) アプリの管理」を参照してください。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Microsoft Store for Business アプリ
Microsoft Store for Business にサインアップしていない場合は、アプリを購入するときにサインアップできます。 アプリを作成した後、それらを Microsoft Managed Desktop と同期できます。 

**Microsoft Store for Business からアプリを購入するには**

1. Microsoft Store [for Business 管理者アカウント](https://businessstore.microsoft.com) を使用して Microsoft Store for Business にサインインします。
2. [自分 **のグループのショップ] を選択します**。
3. 検索を使用して、目的のアプリを検索し、アプリを選択します。
4. 製品の詳細で、[アプリの取得 **] を選択します**。 Microsoft Store は、組織の **製品にアプリ** を追加します。

**Intune と Microsoft Store for Business の間で強制的に同期するには**
1. Microsoft Endpoint Manager 管理センター [にサインインします](https://go.microsoft.com/fwlink/?linkid=2109431)。
2. [**テナント管理**  >  **コネクタとトークン**  >  **Microsoft Store for Business] を選択します**。
3. [ **同期] を** 選択して、Microsoft ストアから Intune に購入したアプリを取得します。

**Intune と Microsoft Store for Business の同期がアクティブな状態を確認するには**
1. Microsoft Store [for Business 管理者アカウント](https://businessstore.microsoft.com) を使用して Microsoft Store for Business にサインインします。
2. [管理 **] を選択します**。
3. [設定 **] を選択** し、[配布] **を選択します**。
4. [ **管理ツール]** で、Intune が一覧に表示され、状態が [アクティブ] である必要 **があります**。  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>手順 2: Azure ADグループを作成する

アプリごとに 3 つの Azure ADグループを作成します。 次の表に、必要なグループ (利用可能、必須、アンインストール) の概要を示します。 

アプリの割り当ての種類 |    グループの使用    | Azure の名前AD例
--- | --- | ---
Available |  アプリは、ポータル サイト アプリまたは Web サイトから利用できます。 | MMD – *アプリ名* – 使用可能
必須 |  アプリは、選択したグループ内のデバイスにインストールされます。 | MMD – *アプリ名* – 必須
Uninstall |  アプリは、選択したグループ内のデバイスからアンインストールされます。 | MMD – *アプリ名* – アンインストール

これらのグループにユーザーを追加して、アプリを利用可能にするか、アプリをインストールするか、Microsoft Managed Desktop デバイスからアプリを削除します。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>手順 3: ユーザーにアプリを割り当てる

**アプリをユーザーに割り当てるには**

1. [Microsoft Managed Desktop Admin ポータルにサインインします](https://aka.ms/mmdportal)。
2. [管理デスクトップ] ウィンドウで、[アプリ] を **選択します**。
3. [アプリ] ワークロードで、ユーザーを割り当てるアプリを選択し、[ユーザー グループの割り当て **] を選択します**。
4. 特定のアプリで、割り当ての種類 (利用可能、必須、アンインストール) を選択し、適切なグループを割り当てる。
5. [アプリの割り当て] ウィンドウで **、[OK] を選択します**。


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop の使用を開始する手順

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