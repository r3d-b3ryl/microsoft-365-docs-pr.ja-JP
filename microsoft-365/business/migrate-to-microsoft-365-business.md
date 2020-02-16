---
title: Office 365 Business Premium からの Microsoft 365 Business へのアップグレード
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Office 365 Business Premium から Microsoft 365 Business にビジネスをアップグレードする手順。
ms.openlocfilehash: e17ac2658c7276ba4a77de371847343866815c42
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065285"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a>Office 365 Business Premium からの Microsoft 365 Business へのアップグレード

Office [365 for business のサブスクリプション](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)(たとえば、Office 365 business Premium) をご利用の場合は、Microsoft 365 business へのアップグレードが容易にできます。 次のものを追加する場合は、Microsoft 365 Business にアップグレードします。 
- Windows 10 Pro (Windows 8 以降を実行している Pc に対して)
- デバイス上のビジネスデータを管理する単純なコントロール
- 高度なセキュリティ機能。
Microsoft 365 Business の詳細については、「 [Microsoft.com](https://www.microsoft.com/microsoft-365/business) 」を参照してください。

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a>Office 365 Business Premium と Microsoft 365 Business の違いは何ですか。
これらの2つのプランを[Microsoft 365 Business Service の説明](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)に並べて比較しました。 

## <a name="before-you-get-started"></a>使用を開始する前に

- **いつアップグレードを選択する必要がありますか。** アップグレードは、1つのプランに割り当てられた**すべてのユーザー**をアップグレードする場合に最適です。 [アップグレード] を選択すると、すべてのプランユーザーが同時に別のプランに切り替えられます。 1つのプランに割り当てられたすべてのユーザーをアップグレードしない場合は、新しいプラン (この場合は Microsoft 365 Business) のライセンスを購入し、アップグレードするユーザーごとに[これらのライセンスを個別に割り当て](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)ます。 
- **一部のアドオンでアップグレードができない場合がある**アップグレードを開始しようとしていて、続行できないアドオンがある場合は、最初にアドオンを削除してから、後で必要になったときに追加することができます。 
- **プランを前払いした場合**プリペイドプランには、簡単なアップグレードパスはありません。 お客様は、ストアで購入したプロダクト ID を使用してプランを設定することにより、プリペイドプランを所有しているかどうかを確認できます。 パートナーに連絡するか、Microsoft ストアに移動するか、プリペイドプランの期限が切れて新しいプランに切り替えるまで待機します。

## <a name="upgrade-to-microsoft-365-business"></a>Microsoft 365 Business へのアップグレード
[新しい管理センター](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)で、次の手順を実行してライセンスを購入します。
1. で<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>管理センターにサインインします。
2. ナビゲーションウィンドウに移動して、[ **Billing** \> **Products & Services**] を選択します。 Office 365 サブスクリプションを検索し、それを選択して詳細を表示します。 

    ![スクリーンショットは、管理センターでサブスクリプションを検索して選択する方法を示しています。](../media/FindYourSubscription.png)

3. 次のページで、[**アップグレード**] を選択します。 

      ![管理センターで、[アップグレード] を選択する場所がスクリーンショットに示されています。](../media/SelectUpgrade.png)

  > [!NOTE]
  > **Azure Active Directory でのグループベースのライセンスでサブスクリプションのアップグレードがサポート**されていないというメッセージが表示された場合は、非常に大規模な組織でない限り、これは無視しても問題ありません。 このオプションを選択した組織では、グループベースのライセンスを使用していることに注意してください。

4. 次に、アップグレード可能な Office プランの一覧を表示できます。 この場合は、Microsoft 365 のビジネスプランを検索してください。 このプランに含まれているすべての Office アプリとサービスを表示するには、下にスクロールします。 [ **Microsoft 365 business**] で、[**アップグレード**] を選択して、カートに microsoft 365 Business を追加します。
5. カート内:
    1. すべての現在のユーザーのライセンスが自動的に追加されます。 ライセンスの数が増える場合は、[それらのライセンスを個別に購入して割り当てる](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)必要があります。  
    2. 支払い方法は、月単位または年単位で調整できます。 ドロップダウンメニューから選択します。
6. [**チェックアウトへ移動**] を選択すると、このアカウントの支払い方法など、購入の概要が表示されます。 また、プロモーションコードを用意している場合は、ここで追加することもできます。
7. [**注文**] を選択して購入を完了します。
新しいサービスプランを設定するには、Microsoft に数分かかります。 進行状況を確認するには、[**アップグレード状態の確認**] を選択します。 
1. プランの準備が整ったら、管理センターで追加のセットアップ手順を完了する必要がある場合があります。 ナビゲーションウィンドウで、[**ホーム**] を選択して、追加のセットアップ手順を完了します。

> [!NOTE]
> 不要になった Office 365 ライセンスに対して、日割り計算が行われます。 銀行口座またはクレジットカードは、新しいプランを設定してから2日後に課金されます。
  
## <a name="protect-user-devices-and-files"></a>ユーザーのデバイスとファイルを保護する

これで、Microsoft 365 Business のライセンスが割り当てられました。次に、デバイスとファイルの保護を開始するための手順を完了します。 管理センターのナビゲーションウィンドウには、いくつかの新しいオプションを追加します。
  
1. 管理センターのナビゲーションウィンドウで、[**デバイス** \> **ポリシー**] に移動します。
    
2. [**デバイスポリシー** ] ページで、[**追加**] を選択します。
    
3. [**ポリシーの追加**] ウィンドウで、ポリシーに名前 (たとえば、作業ファイルを保護する) を指定し、ドロップダウンリストから**ポリシーの種類**を選択します。 
    
    Android および iPhone デバイス上のファイルを保護するためのアプリケーションポリシーおよび Windows 10 を設定し、会社が所有する Windows 10 デバイスのデバイス構成ポリシーを設定できます。 詳細については、次のリンクを参照してください。
    
  - [Android または iOS デバイスのアプリ保護設定を設定する](app-protection-settings-for-android-and-ios.md)
    
  - [Windows 10 デバイスのアプリケーション保護設定を設定する](protection-settings-for-windows-10-devices.md)
    
  - [Windows 10 Pc のデバイス保護設定を設定する](protection-settings-for-windows-10-pcs.md)
    
  
4. ポリシーを設定すると、ユーザーはデバイスをセットアップできるようになります。
    
  - Windows デバイスが Windows Pro Creator の更新プログラムを使用していない場合は、[それらを Windows Pro Creator update にアップグレード](upgrade-to-windows-pro-creators-update.md)する必要があります。
    
  - Windows デバイスの手順については、「 [Microsoft 365 Business ユーザーの windows デバイスをセットアップ](set-up-windows-devices.md)する」を参照してください。 
    
  - Android フォンおよび iPhones の手順については、「 [Microsoft 365 Business ユーザー向けのモバイルデバイスのセットアップ](set-up-mobile-devices.md)」を参照してください。 
