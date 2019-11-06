---
title: Office 365 Business Premium からの Microsoft 365 Business へのアップグレード
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
ms.openlocfilehash: 1e337b908f848da1d33cbd8e662652550d302b14
ms.sourcegitcommit: 0fa897d06b664c0ed005817752da1426d4ee17cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "38002129"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a>Office 365 Business Premium からの Microsoft 365 Business へのアップグレード

Office [365 for business のサブスクリプション](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)(たとえば、Office 365 business Premium) をご利用の場合は、Microsoft 365 business へのアップグレードが容易にできます。 次のものを追加する場合は、Microsoft 365 Business にアップグレードします。 
- Windows 10 Pro (Windows 8 以降を実行している Pc に対して)
- デバイス上のビジネスデータを管理する単純なコントロール
- 高度なセキュリティ機能。
Microsoft 365 Business の詳細については、「 [Microsoft.com](https://www.microsoft.com/microsoft-365/business) 」を参照してください。

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a>Office 365 Business Premium と Microsoft 365 Business の違いは何ですか。
これらの2つのプランを[Microsoft 365 Business service の説明](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)に並べて比較しました。 

1. 新しいライセンスを購入すると、これが初めての場合は、Microsoft 365 Business のセットアップバナーが管理センターの一番上に表示されます。
    
    > [!NOTE]
    > セットアップバナーは新しいユーザーを追加し、新しいドメインを追加して、新しいユーザーのメールを移行する機会です。 この操作を行わない場合でも、ウィザードを使用して [既定のオプション] を選択し、管理者のホームページから非表示にすることをお勧めします。 
  
   ![Microsoft 365 Business で [セットアップの開始] を選択して、バナーをセットアップする準備ができました。](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    [ **セットアップの開始**] を選びます。
    
2. [**サインインとメールのカスタマイズ**] ページで、この機会を使用してサブスクリプションに別のドメインを追加する場合は、[**既に所有し**ているドメインの接続] を選択してドメインを追加します。 
    
    既にドメインを設定している場合は、2番目のフィールドには、**メールの**_ドメイン名_\> **を使用し続けて** \<サインインするように指示します。   サブスクリプションを使用してドメインをセットアップしていない場合は **、引き続き** \<_会社の name.onmicrosoft.com_ \>を使用して**電子メールを送信**し、サインインしてください。  
    
    **次へ**を選択します。
    
    ![[サインインとメールのカスタマイズ] ページで、ドメインを追加するか、使用しているドメインを使用するかを選択します。](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. [新しい**ユーザーの追加**] ページで、新しいユーザーを追加することができます。これには、Microsoft 365 Business のライセンスを割り当てる必要があります。 
    
    新しい従業員を追加して、既存のユーザーにライセンスを割り当てる場合は、[**次へ**] を選択します。
    
4. [**メールメッセージの移行**] ページで、手順3で追加した新しいユーザーのいずれかに対して電子メールを移行することを選択できます。 この手順は省略することもできます。 **次へ**を選択します。
    
5. 最後のページで [**管理センターに移動**します] を選択して、セットアップを続行します。
    
6. 管理センターで、[**ユーザー** \> ] [**アクティブなユーザー**] に移動します。
    
7. **Microsoft 365 Business** license を割り当てるユーザーを選択し、[**製品ライセンス**] の横にある [**編集**] を選択します。
    
    ![ユーザーカードで、[製品ライセンス] の横にある [編集] を選択します。](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
## <a name="before-you-get-started"></a>開始する前に

- **いつアップグレードを選択する必要がありますか。** アップグレードは、1つのプランに割り当てられた**すべてのユーザー**をアップグレードする場合に最適です。 [アップグレード] を選択すると、すべてのプランユーザーが同時に別のプランに切り替えられます。 1つのプランに割り当てられたすべてのユーザーをアップグレードしない場合は、新しいプラン (この場合は Microsoft 365 Business) のライセンスを購入し、アップグレードするユーザーごとに[これらのライセンスを個別に割り当て](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)ます。 
- **一部のアドオンはアップグレードを妨げる可能性があります**アップグレードを開始しようとしていて、続行できないアドオンがある場合は、最初にアドオンを削除してから、後で必要に応じて追加することができます。 
- **プランを前払いした場合**プリペイドプランには、簡単なアップグレードパスはありません。 お客様は、ストアで購入したプロダクト ID を使用してプランを設定することにより、プリペイドプランを所有しているかどうかを確認できます。 パートナーに連絡するか、Microsoft ストアに移動するか、プリペイドプランの期限が切れて新しいプランに切り替えるまで待機します。

## <a name="upgrade-to-microsoft-365-business"></a>Microsoft 365 Business へのアップグレード
[新しい管理センター](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)で、次の手順を実行してライセンスを購入します。
1. で<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>管理センターにサインインします。
2. ナビゲーションウィンドウに移動して、[ **Billing** \> **Products & Services**] を選択します。 Office 365 サブスクリプションを検索し、それを選択して詳細を表示します。 

    ![スクリーンショットは、管理センターでサブスクリプションを検索して選択する方法を示しています。](media/FindYourSubscription.png)

3. 次のページで、[**アップグレード**] を選択します。 

      ![管理センターで、[アップグレード] を選択する場所がスクリーンショットに示されています。](media/SelectUpgrade.png)

  > [!NOTE]
  > 「Azure Active Directory でのサブスクリプションのアップグレードは、グループベースのライセンスでサポートされていません」というメッセージが表示される場合は、非常に大規模な組織でない限り、これは無視しても問題ありません。 このオプションを選択した組織では、グループベースのライセンスを使用していることに注意してください。

4. 次に、アップグレード可能な Office プランの一覧を表示できます。 この場合は、Microsoft 365 のビジネスプランを検索してください。 このプランに含まれているすべての Office アプリとサービスを表示するには、下にスクロールします。 [ **Microsoft 365 business**] で、[**アップグレード**] を選択して、カートに microsoft 365 Business を追加します。
5. カート内:
    1. すべての現在のユーザーのライセンスがカートに自動的に追加されます。 より多くのライセンスが必要な場合は、[これらのライセンスを個別に購入して割り当てる](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)必要があります。  
    2. 月々または年間の支払方法を調整できます。 ドロップダウンメニューから選択します。
6. [**チェックアウトへ移動**] を選択すると、このアカウントの支払い方法など、購入の概要が表示されます。 また、プロモーションコードを用意している場合は、ここで追加することもできます。
7. [**注文**] を選択して購入を完了します。
新しいサービスプランを設定するには、Microsoft に数分かかります。 進行状況を確認するには、[**アップグレード状態の確認**] を選択します。 
1. プランの準備が整ったら、管理センターで追加のセットアップ手順を完了する必要がある場合があります。 ナビゲーションウィンドウで、[**ホーム**] を選択して、追加のセットアップ手順を完了します。

> [!NOTE]
> 不要になった Ofifce 365 ライセンスに対して、日割り計算が行われます。 銀行口座またはクレジットカードは、新しいプランを設定してから2日後に課金されます。
  
## <a name="protect-user-devices-and-files"></a>ユーザーのデバイスとファイルを保護する

これで、Microsoft 365 Business のライセンスが割り当てられました。次に、デバイスとファイルの保護を開始するための手順を完了します。 管理センターのナビゲーションウィンドウには、新しいオプションがいくつか用意されています。
  
1. 管理センターのナビゲーションウィンドウで、[**デバイス** \> **ポリシー**] に移動します。
    
2. [**デバイスポリシー** ] ページで、[**追加**] を選択します。
    
3. [**ポリシーの追加**] ウィンドウで、ポリシーに名前 (たとえば、作業ファイルを保護する) を指定し、ドロップダウンから**ポリシーの種類**を選択します。 
    
    Android および iPhone デバイス上のファイルを保護するためのアプリケーションポリシーおよび Windows 10 を設定し、会社が所有する Windows 10 デバイスのデバイス構成ポリシーを設定できます。 詳細については、次のリンクを参照してください。
    
  - [Android または iOS デバイスのアプリ保護設定を設定する](app-protection-settings-for-android-and-ios.md)
    
  - [Windows 10 デバイスのアプリケーション保護設定を設定する](protection-settings-for-windows-10-devices.md)
    
  - [Windows 10 Pc のデバイス保護設定を設定する](protection-settings-for-windows-10-pcs.md)
    
  
4. ポリシーを設定すると、ユーザーはデバイスをセットアップできるようになります。
    
  - Windows デバイスが Windows Pro Creator の更新プログラムを使用していない場合は、[それらを Windows Pro Creator update にアップグレード](upgrade-to-windows-pro-creators-update.md)する必要があります。
    
  - Windows デバイスの手順については、「 [Microsoft 365 Business ユーザーの windows デバイスをセットアップ](set-up-windows-devices.md)する」を参照してください。 
    
  - Android フォンおよび iPhones の手順については、「 [Microsoft 365 Business ユーザー向けのモバイルデバイスのセットアップ](set-up-mobile-devices.md)」を参照してください。 



