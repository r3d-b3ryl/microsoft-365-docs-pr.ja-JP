---
title: アプリをデバイスに展開する
description: Microsoft Managed Desktop デバイスへのアプリの追加と展開に関する情報。
keywords: Microsoft Managed Desktop、Microsoft 365、サービス、ドキュメント、アプリ、line-of-business アプリ、LOB アプリ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 15b41681d94d8f33176d140ebc00cc74319e69ff
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2021
ms.locfileid: "60334503"
---
# <a name="deploy-apps-to-devices"></a>アプリをデバイスに展開する
Microsoft Managed Desktop へのオンボードの一部には、ユーザーのデバイスへのアプリの追加と展開が含まれます。 Microsoft Managed Desktop ポータルを使用すると、アプリを追加して展開できます。 

全体的なプロセスは次のように表示されます。
1. [Microsoft Managed Desktop](#1)ポータルにアプリを追加する - 既存の業務用 (LOB) アプリ、または Intune と同期した ビジネス向け Microsoft Store からのアプリを指定できます。 
2. [アプリAzure Active Directory (AD)](#2)グループを作成する - これらのグループを使用してアプリの割り当てを管理します。
3. [アプリをユーザーに割り当てる](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>手順 1: Microsoft Managed Desktop ポータルにアプリを追加する
[Win32、または MSI](#lob-apps)ベースのアプリWindowsまたは[ビジネス向け Microsoft Store](#msfb-apps)アプリを Microsoft Managed Desktop に追加し、Microsoft マネージ デスクトップ デバイスに展開できます。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 または Windows MSI ベースのアプリを Microsoft マネージ デスクトップに追加する

ビジネスライン (LOB) アプリを Microsoft マネージ デスクトップ ポータルに追加できます。 Microsoft Managed Desktop デバイスにインストールされているアプリの要件については [、「Microsoft Managed Desktop](../service-description/mmd-app-requirements.md)アプリの要件」を参照してください。

この手順では、追加するアプリの種類を選択し、アプリ ソースを構成してアップロードします。 

**LOB アプリまたはアプリを Microsoft Windows デスクトップ ポータルに追加するには**

Microsoft Managed Desktop ポータルにサインインするか、Intune にサインインしてから Microsoft Managed Desktop を検索できます。 Microsoft Managed Desktop ポータルへのサインインが表示されます。 

1.    [Microsoft Managed Desktop Admin ポータルにサインインします](https://aka.ms/mmdportal)。 
2.    [インベントリ **] で**、[アプリ] **を選択します**。
3.    [アプリ] ワークロードで、[追加] を **選択します**。
4.    [**アプリの追加]** で **、[Line-of-business アプリ**] または [アプリWindows **(Win32) を選択します**。
    - [Line-of-business app] を選択した場合は、「Windows **line-of-business** アプリを [Microsoft Intune](/intune/lob-apps-windows)に追加して構成する」を参照してください。
    - アプリ **(Win32) Windows選択** した場合は [、「Win32](/intune/apps-win32-app-management)アプリの管理」を参照して、アプリの追加と構成Windowsしてください。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>ビジネス向け Microsoft Store アプリ
アプリにサインアップしていないビジネス向け Microsoft Store、アプリを購入するときにサインアップできます。 アプリを作成した後、それらを Microsoft Managed Desktop と同期できます。 

**アプリをアプリから購入ビジネス向け Microsoft Store**

1. 管理者アカウントで[ビジネス向け Microsoft Store](https://businessstore.microsoft.com)サインインビジネス向け Microsoft Storeします。
2. [自分 **のグループのショップ] を選択します**。
3. 検索を使用して目的のアプリを検索し、アプリを選択します。
4. 製品の詳細で、[アプリの取得 **] を選択します**。 Microsoft Store、組織の **製品にアプリ** を追加します。
    
**Intune とデバイス間の同期がアクティブビジネス向け Microsoft Storeするには**
1. 管理者アカウントで[ビジネス向け Microsoft Store](https://businessstore.microsoft.com)サインインビジネス向け Microsoft Storeします。
2. [管理 **] を選択します**。
3. [配布 **設定] を** 選択し、[配布] を **選択します**。
4. [ **管理ツール]** で、Intune が一覧に表示され、状態が [アクティブ] である必要 **があります**。  
    
**Intune とデバイス間の同期を強制的に行ビジネス向け Microsoft Store**
1. Microsoft エンドポイント マネージャー管理センター
2. [**テナント管理**  >  **コネクタとトークン] を**  >  **選択** ビジネス向け Microsoft Store。
3. [**同期を** 有効にする **ビジネス向け Microsoft Store有効にする] を選択すると、Intune でボリューム購入したアプリにアクセスできます。** 
4. 使用する言語を選択し、[**同期**] を選択して、アプリから購入したアプリを Intune Microsoft Store取得します。

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>手順 2: グループAzure ADする

アプリごとに 3 Azure ADグループを作成します。 次の表に、必要なグループ (利用可能、必須、アンインストール) の概要を示します。 

アプリの割り当ての種類 |    グループの使用    | 名前Azure AD例
--- | --- | ---
使用可能 |  アプリは、アプリまたは web サイトポータル サイト利用できます。 | MMD – *アプリ名* – 使用可能
必須 |  アプリは、選択したグループ内のデバイスにインストールされます。 | MMD – *アプリ名* – 必須
アンインストール |  アプリは、選択したグループ内のデバイスからアンインストールされます。 | MMD – *アプリ名* – アンインストール

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

1. [管理ポータル](access-admin-portal.md)にアクセスします。
1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)。
1. [登録後に設定を調整する](conditional-access.md)。
1. [Intune ポータル サイト](company-portal.md)を展開して割り当てます。
1. [ライセンスを割り当てる](assign-licenses.md)。
1. アプリを展開する (この記事)。
1. [デバイスをセットアップする](set-up-devices.md)。
1. [Autopilot と登録ステータス ページの初回実行時エクスペリエンス](esp-first-run.md)のセットアップ。
1. [ユーザー サポート機能を有効にする](enable-support.md)。
1. [ユーザーがデバイスを使えるようにする](get-started-devices.md)。
1. [アプリ制御の使用を開始する](get-started-app-control.md)。


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
