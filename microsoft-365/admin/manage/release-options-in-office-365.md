---
title: 標準または対象指定のリリース オプションを設定する
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Microsoft 365 管理センターで新しい製品と機能の更新プログラムのリリース オプションを設定する方法について説明します。
ms.openlocfilehash: 99a2660af9d8756bf4faf1cf3eddfe142a7c87bf
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114491"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>標準または対象指定のリリース オプションを設定する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

> [!IMPORTANT]
> この記事で説明されている Microsoft 365 更新プログラムは、Microsoft 365、SharePoint Online、および Exchange Online に適用されます。 これらのリリース オプションは、Microsoft 365 への変更をリリースするための最善の方法ですが、すべての時間またはすべての更新プログラムについて保証することはできません。 Microsoft 365 Apps、Skype for Business、Microsoft Teams、および関連サービスには適用されません。 Microsoft 365 アプリのリリース オプションについては [、「Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-channels)アプリの更新プログラム チャネルの概要」を参照してください。

Microsoft 365 では、数年ごとにコストの高い更新プログラムを実行する代わりに、新しい製品の更新プログラムと機能が利用可能になったら、更新プログラムと機能を受け取る必要があります。 組織がこれらの更新プログラムを受信する方法を管理できます。 たとえば、組織が最初に更新プログラムを受信できるよう、早期リリースにサインアップできます。 特定の個人だけが更新プログラムを受け取る場合に指定できます。 または、既定のリリース スケジュールのままにして、後で更新プログラムを受信することもできます。 この記事では、さまざまなリリース オプションと、それらを組織で使用する方法について説明します。

## <a name="how-it-works---release-validation"></a>しくみ - リリースの検証

新しいリリースは、最初に機能チームによってテストおよび検証され、次に Microsoft 365 機能チーム全体、その後に Microsoft のすべてによって検証されます。 内部テストと検証が終わったら、次の手順は参加しているお客様に向けた **対象指定リリース** (以前は先行リリースと呼ばれていました) です。 各リリース リングで、Microsoft はフィードバックを収集し、主要な利用状況メトリックを監視することでさらに品質を検証します。 この革新的な一連の検証は、全世界のリリースの信頼性を最大限に高めるためにあります。 各リリースを、次の図で示します。 
  
![Microsoft 365 のリリース検証リング](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
重要な更新プログラムについては、最初に [Microsoft 365 ロードマップによってお客様に通知されます](https://products.office.com/business/office-365-roadmap)。 更新プログラムの展開が近づくと [、Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)メッセージ センターから通信されます。

> [!NOTE]
> 管理センターからメッセージ センターにアクセスするには、Microsoft 365 または Azure AD アカウントが [必要です](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)。 Microsoft 365 ホーム プランのユーザーには管理センターが設定されていない。


## <a name="standard-release"></a>標準リリース

これは、最新の更新プログラムがすべてのユーザーに広くリリースされると、ユーザーが最新の更新プログラムを受け取る既定のオプションです。
  
ユーザーの大半を **Standard** リリースに残し、IT のプロとパワー ユーザーを対象指定リリースに残し、新機能を評価し、ビジネス ユーザーとエグゼクティブをサポートするためのチームを準備する方法が良い方法です。 
  
> [!NOTE]
> 対象指定リリースから標準リリースに切り替えた場合、ユーザーは標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。 
  
## <a name="targeted-release"></a>対象となるリリース

このオプションでは、お客様とお客様のユーザーは最新の更新プログラムを先に確認できて、早い時点でフィードバックをすることで製品像の決定に協力できます。更新プログラムを個人で早く受信するか、組織全体で早く受信するかを選ぶことができます。
  
> [!IMPORTANT]
> 大規模な更新プログラムまたは複雑な更新プログラムは、悪影響を受けるユーザーがいないようにするために他の更新プログラムに比べて時間がかかる場合があります。 リリースは、予定どおりになる保証はありません。 
  
### <a name="targeted-release-for-entire-organization"></a>組織全体の対象指定リリース

このオプション [の管理センターで](#set-up-the-release-option-in-the-admin-center) リリース オプションを設定すると、すべてのユーザーに対象指定リリース エクスペリエンスが提供されます。 ユーザー数が 300 を超える組織では、このオプションにテスト サブスクリプションを使用することをお勧めします。 テスト サブスクリプションについては、Microsoft の担当者にお問い合わせください。 
  
### <a name="targeted-release-for-selected-users"></a>選択したユーザーの対象指定リリース

このオプション [の管理センター](#set-up-the-release-option-in-the-admin-center) でリリース オプションを設定する場合は、特定のユーザー (通常はパワー ユーザー) を定義して、機能への早期アクセスを受け取る必要があります。 
  
## <a name="benefits-of-targeted-release"></a>対象指定リリースの利点

対象指定リリースでは、管理者、変更マネージャー、または Microsoft 365 更新プログラムを担当する他のユーザーは、次の方法で今後の変更に備えます。
  
- 組織内のすべてのユーザーにリリースされる前に、新しい更新プログラムをテストおよび検証する。
    
- 更新プログラムが全世界でリリースされる前に、ユーザー通知およびドキュメントを準備する。
    
- 今後の変更に関する社内ヘルプ デスクを準備する。
    
- コンプライアンスとセキュリティ レビューに合格する。
    
- 機能制御を必要に応じて使用して、エンド ユーザーに対する更新プログラムのリリースを制御する。
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>管理センターでリリース オプションを設定する

次の手順に従って、組織が Microsoft 365 更新プログラムを受信する方法を変更できます。 オプトインするには、Microsoft 365 のグローバル管理者である必要があります。
  
> [!IMPORTANT]
> Microsoft 365 で以下の変更が有効にな最大 24 時間かかる場合があります。 対象指定リリースをいったん有効にした後に無効にすると、予定された標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。 
  
1. 管理センターで、[Settings Org Setting] に移動し、[Organization profile] タブの [Release  >   **preferences] を選択します**。 

5. 対象指定リリースを無効にするには、[標準リリース] **を** 選択し、[変更の保存] **を選択します**。 
    
6. 組織内のすべてのユーザーの対象指定リリースを有効にするには、すべてのユーザーの対象指定リリースを選択し、[変更の保存]**を選択します**。 
    
7. 組織内の一部のユーザーの対象指定リリースを有効にするには、選択したユーザーの対象指定リリースを選択し、[変更の保存]**を選択します**。 
    
8. ユーザー **を一度に** 1 人追加する場合は [ユーザーの選択] を選択し、ユーザーを一括して追加する場合は [ユーザーのアップロード] を選択します。
    
9. ユーザーの追加が完了したら、[変更の保存] **を選択します**。


  
## <a name="learn-more"></a>詳細情報

Microsoft 365 メッセージ センターでメッセージを管理して、今後の[Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)の更新プログラムとリリースに関する通知を受け取る方法について説明します。 [](https://docs.microsoft.com/office365/admin/manage/message-center)
