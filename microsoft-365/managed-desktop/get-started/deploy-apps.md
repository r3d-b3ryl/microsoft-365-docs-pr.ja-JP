---
title: アプリをデバイスに展開する
description: Microsoft マネージドデスクトップデバイスへのアプリの追加および展開に関する情報。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント、アプリ、基幹業務アプリ、LOB アプリ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd6efc56441cfbe8a05404319246c5e0bbe10ab
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44046330"
---
# <a name="deploy-apps-to-devices"></a>アプリをデバイスに展開する
Microsoft Managed Desktop へのオンボードの一部には、ユーザーのデバイスへのアプリの追加と展開が含まれます。 Microsoft マネージドデスクトップポータルを使用している場合は、アプリを追加して展開することができます。 

全体的なプロセスは次のようになります。
1. [Microsoft マネージドデスクトップポータルへのアプリの追加](#1)-既存の基幹業務 (LOB) アプリ、または Intune と同期したビジネス向け Microsoft Store のアプリにすることができます。 
2. [アプリの割り当て用に Azure Active Directory (AD) グループを作成](#2)する-これらのグループを使用して、アプリの割り当てを管理します。
3. [ユーザーにアプリを割り当てる](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>手順 1: Microsoft マネージドデスクトップポータルにアプリを追加する
Microsoft マネージドデスクトップには、 [Win32、WINDOWS MSI ベースのアプリ](#lob-apps)、または[Microsoft Store for Business アプリ](#msfb-apps)を追加し、それを microsoft マネージドデスクトップデバイスに展開することができます。

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップへの Win32 または Windows MSI ベースのアプリ

基幹業務 (LOB) アプリを Microsoft マネージドデスクトップポータルに追加できます。 Microsoft マネージドデスクトップデバイスにインストールされているアプリの要件の詳細については、「 [Microsoft Managed desktop app の要件](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)」を参照してください。

この手順では、追加するアプリの種類を選択してから、アプリソースを構成およびアップロードします。 

**LOB アプリまたは Windows アプリを Microsoft マネージドデスクトップポータルに追加するには**

Microsoft マネージドデスクトップポータルにサインインするか、Intune にサインインして、Microsoft Managed Desktop を検索することができます。 Microsoft マネージドデスクトップポータルへのサインインを表示します。 

1.    [Microsoft Managed Desktop 管理ポータル](https://aka.ms/mmdportal)にサインインします。 
2.    [**インベントリ**] で、[**アプリ**] を選択します。
3.    [アプリのワークロード] で、[**追加**] を選択します。
4.    [**アプリの追加**] で、[**基幹業務アプリ**] または [ **Windows アプリ (Win32)**] を選択します。
    - 基幹**業務アプリ**を選択した場合は、基幹業務アプリを追加して構成する手順については、「 [Windows の基幹業務アプリを Microsoft Intune に追加](https://docs.microsoft.com/intune/lob-apps-windows)する」を参照してください。
    - **Windows アプリ (win32)** を選択した場合は、「 [win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) 」を参照してください。 windows アプリの追加および構成に関する指示については、を参照してください。

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>ビジネス向け Microsoft Store アプリ
Microsoft Store for Business にサインアップしていない場合は、アプリの購入時にサインアップできます。 アプリを用意したら、それらを Microsoft マネージドデスクトップと同期することができます。 

**ビジネス向け Microsoft Store からアプリを購入するには**

1. Business 管理者アカウントの Microsoft Store を使用して、 [Microsoft store For business](https://businessstore.microsoft.com)にサインインします。
2. [**自分のグループのショッピング**] を選択します。
3. 検索を使用して目的のアプリを見つけ、アプリを選択します。
4. [製品の詳細] で、[**アプリの取得**] を選択します。 Microsoft Store では、組織の**製品**にアプリが追加されます。

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
1. Business 管理者アカウントの Microsoft Store を使用して、 [Microsoft store For business](https://businessstore.microsoft.com)にサインインします。
2. [**管理**] を選択します。
3. [**設定**] を選択し、[**配布**] を選択します。
4. [**管理ツール**] で、Intune が表示され、状態が [**アクティブ**] になっていることを確認します。  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>手順 2: Azure AD グループを作成する

アプリごとに3つの Azure AD グループを作成します。 次の表に、必要なグループ (利用可能、必要、およびアンインストール) の概要を示します。 

アプリの割り当ての種類 |    グループの使用    | Azure AD 名の例
--- | --- | ---
Available |  アプリは、会社のポータルアプリまたは web サイトから入手できます。 | MMD –*アプリ名*–利用可能
必須 |  アプリは、選択したグループのデバイスにインストールされます。 | MMD –*アプリ名*–必須
Uninstall |  選択したグループのデバイスからアプリがアンインストールされます。 | MMD –*アプリ名*–アンインストール

これらのグループにユーザーを追加して、アプリを利用できるようにするか、アプリをインストールするか、Microsoft マネージドデスクトップデバイスからアプリを削除します。 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>手順 3: ユーザーにアプリを割り当てる

**アプリをユーザーに割り当てるには**

1. [Microsoft Managed Desktop 管理ポータル](https://aka.ms/mmdportal)にサインインします。
2. [管理されたデスクトップ] ウィンドウで、[**アプリ**] を選択します。
3. [アプリのワークロード] で、ユーザーの割り当て先となるアプリを選択し、[**ユーザーグループの割り当て**] を選択します。
4. 特定のアプリについて、割り当ての種類 (利用可能、必須、アンインストール) を選択し、適切なグループを割り当てます。
5. [アプリの割り当て] ウィンドウで、[ **OK]** を選択します。


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップの使用を開始する手順

1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)
2. [条件付きアクセスを調整する](conditional-access.md)
3. [ライセンスを割り当てる](assign-licenses.md)
4. [Intune 会社ポータルを展開する](company-portal.md)
5. [Enterprise State Roaming を有効にする](enterprise-state-roaming.md)
6. [デバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. アプリを展開する (このトピック)


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
