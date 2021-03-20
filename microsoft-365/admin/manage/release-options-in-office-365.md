---
title: 標準リリースオプションまたはターゲット リリース オプションを設定する
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
ms.openlocfilehash: f500aac89495c55d27fc4afb699254653786422d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915208"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>標準リリースオプションまたはターゲット リリース オプションを設定する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。

::: moniker-end

> [!IMPORTANT]
> この記事で説明する Microsoft 365 更新プログラムは、Microsoft 365、SharePoint Online、および Exchange Online に適用されます。 これらのリリース オプションは、Microsoft 365 への変更をリリースするための最善の努力の方法ですが、すべての時間またはすべての更新プログラムについて保証することはできません。 Microsoft 365 Apps、Skype for Business、Microsoft Teams、および関連サービスには適用されません。 Microsoft 365 Apps のリリース オプションの詳細については [、「Microsoft 365](/deployoffice/overview-update-channels)Apps の更新プログラム チャネルの概要」を参照してください。

Microsoft 365 では、数年ごとにコストの高い更新プログラムを実行する代わりに、新しい製品の更新プログラムと機能が利用できると受け取る。 組織がこれらの更新プログラムを受け取る方法を管理できます。 たとえば、組織が最初に更新プログラムを受け取る前に、早期リリースにサインアップできます。 特定の個人だけが更新プログラムを受け取る方法を指定できます。 または、既定のリリース スケジュールのままで、後で更新プログラムを受信することもできます。 この記事では、さまざまなリリース オプションと、それらを組織で使用する方法について説明します。

## <a name="how-it-works---release-validation"></a>しくみ - リリースの検証

すべての新しいリリースは、最初に機能チームによってテストおよび検証され、次に Microsoft 365 機能チーム全体によって、その後に Microsoft のすべてが続きます。 内部テストと検証が終わったら、次の手順は参加しているお客様に向けた **対象指定リリース** (以前は先行リリースと呼ばれていました) です。 各リリース リングで、Microsoft はフィードバックを収集し、主要な利用状況メトリックを監視することでさらに品質を検証します。 この革新的な一連の検証は、全世界のリリースの信頼性を最大限に高めるためにあります。 各リリースを、次の図で示します。 
  
![Microsoft 365 の検証リングをリリースする](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
重要な更新プログラムについては、Microsoft [365 ロードマップによってお客様に最初に通知されます](https://products.office.com/business/office-365-roadmap)。 更新プログラムが展開に近づくにつれて [、Microsoft 365 メッセージ](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)センターを通じて通信されます。

> [!NOTE]
> 管理センターからメッセージ センターにアクセスするには、Microsoft 365 または Azure ADアカウントが [必要です](/office365/admin/admin-overview/about-the-admin-center)。 Microsoft 365 ホーム プランのユーザーには管理センターが設定されていない。


## <a name="standard-release"></a>標準リリース

これは、ユーザーがすべての顧客に広範にリリースされると、ユーザーが最新の更新プログラムを受け取る既定のオプションです。
  
優れた方法は、標準リリースおよび IT  Pros および Power Users の大部分のユーザーをターゲット リリースに残して、新機能を評価し、ビジネス ユーザーとエグゼクティブをサポートするためのチームを準備する方法です。 
  
> [!NOTE]
> 対象指定リリースから標準リリースに切り替えた場合、ユーザーは標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。 
  
## <a name="targeted-release"></a>対象となるリリース

このオプションでは、お客様とお客様のユーザーは最新の更新プログラムを先に確認できて、早い時点でフィードバックをすることで製品像の決定に協力できます。更新プログラムを個人で早く受信するか、組織全体で早く受信するかを選ぶことができます。
  
> [!IMPORTANT]
> 大規模な更新プログラムまたは複雑な更新プログラムは、悪影響を受けるユーザーがいないようにするために他の更新プログラムに比べて時間がかかる場合があります。 リリースは、予定どおりになる保証はありません。 
  
### <a name="targeted-release-for-entire-organization"></a>組織全体の対象指定リリース

管理センター [でこのオプションのリリース](#set-up-the-release-option-in-the-admin-center) オプションを設定すると、すべてのユーザーが対象のリリース エクスペリエンスを取得します。 ユーザー数が 300 を超える組織では、このオプションにテスト サブスクリプションを使用することをお勧めします。 テスト サブスクリプションについては、Microsoft の担当者にお問い合わせください。 
  
### <a name="targeted-release-for-selected-users"></a>選択したユーザーの対象指定リリース

このオプション [の管理センター](#set-up-the-release-option-in-the-admin-center) でリリース オプションを設定する場合は、特定のユーザー (通常は電源ユーザー) を定義して、機能と機能への早期アクセスを受け取る必要があります。 
  
## <a name="benefits-of-targeted-release"></a>対象指定リリースの利点

対象のリリースでは、管理者、変更管理者、または Microsoft 365 の更新プログラムを担当する他の誰でも、次の変更に対応できます。
  
- 組織内のすべてのユーザーにリリースされる前に、新しい更新プログラムをテストおよび検証する。
    
- 更新プログラムが全世界でリリースされる前に、ユーザー通知およびドキュメントを準備する。
    
- 今後の変更に関する社内ヘルプ デスクを準備する。
    
- コンプライアンスとセキュリティ レビューに合格する。
    
- 機能制御を必要に応じて使用して、エンド ユーザーに対する更新プログラムのリリースを制御する。
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>管理センターでリリース オプションを設定する

次の手順に従って、組織が Microsoft 365 更新プログラムを受け取る方法を変更できます。 オプトインするには、Microsoft 365 のグローバル管理者である必要があります。
  
> [!IMPORTANT]
> Microsoft 365 で以下の変更を有効にするには、最大 24 時間かかる場合があります。 対象指定リリースをいったん有効にした後に無効にすると、予定された標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。 
  
1. 管理センターで、[設定] [組織の設定] に移動し、[組織プロファイル] タブの [基本設定のリリース  >  ]**を選択します**。

5. 対象リリースを無効にするには、[標準リリース] **を選択し**、[変更の保存] **を選択します**。 
    
6. 組織内のすべてのユーザーの対象リリースを有効にするには、[すべてのユーザーの対象リリース] を選択し、[変更の保存]**を選択します**。 
    
7. 組織内の一部のユーザーの対象リリースを有効にするには、[選択したユーザーの対象リリース] を選択し、[変更の保存]**を選択します**。 
    
8. [ **ユーザーを一度** に 1 人追加するユーザーを選択する] または [ユーザーを **アップロード** して一括で追加する] を選択します。
    
9. ユーザーの追加が完了したら、[変更の保存] **を選択します**。


  
## <a name="learn-more"></a>詳細情報

Microsoft 365 メッセージ センターでメッセージを管理して、今後の[Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)の更新プログラムとリリースに関する通知を受け取る方法について説明します。 [](/office365/admin/manage/message-center)