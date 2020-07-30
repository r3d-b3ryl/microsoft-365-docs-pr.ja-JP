---
title: 標準または対象指定リリースオプションを設定する
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
description: Microsoft 365 管理センターで新しい製品および機能の更新プログラムのリリースオプションをセットアップする方法について説明します。
ms.openlocfilehash: 3baec050f33893357b25c832552643cf3a6d10d0
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502881"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>標準または対象指定リリースオプションを設定する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更されました。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

Microsoft 365 では、数年ごとに費用のかかる更新プログラムを実行する代わりに、新しい製品の更新プログラムと機能が提供されます。 組織がこれらの更新を受信する方法を管理できます。 たとえば、初期リリースにサインアップして、組織が最初に更新を受け取るようにすることができます。 特定の個人のみが更新を受信するように指定できます。 または、[既定のリリーススケジュール] をそのまま使用し、更新プログラムを後で受け取ることができます。 この記事では、さまざまなリリースオプションと、それらを組織で使用する方法について説明します。
  
> [!IMPORTANT]
> この記事に記載されている Microsoft 365 更新プログラムは、Microsoft 365、SharePoint Online、および Exchange Online に適用されます。 これらは、Skype for Business および関連するサービスには適用されません。 これらのリリースオプションは、Microsoft 365 への変更をリリースするための最善の方法ですが、常に、またはすべての更新プログラムに対して保証することはできません。 

> [!NOTE]
> アプリケーションの更新プログラムチャネルの詳細については、「 [Microsoft 365 アプリの更新プログラムチャネルの概要](https://docs.microsoft.com/deployoffice/overview-update-channels)」を参照してください。 
  
## <a name="how-it-works---release-validation"></a>しくみ - リリースの検証

新しいリリースはすべて、最初に機能チームによってテストおよび検証され、次に Microsoft 365 機能チーム全体によって、その後にすべての Microsoft が評価されます。 内部テストと検証が終わったら、次の手順は参加しているお客様に向けた **対象指定リリース** (以前は先行リリースと呼ばれていました) です。 各リリース リングで、Microsoft はフィードバックを収集し、主要な利用状況メトリックを監視することでさらに品質を検証します。 この革新的な一連の検証は、全世界のリリースの信頼性を最大限に高めるためにあります。 各リリースを、次の図で示します。 
  
![Microsoft 365 のリリース検証リング](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
重要な更新プログラムについては、お客様には[Microsoft 365 ロードマップ](https://products.office.com/business/office-365-roadmap)による通知が最初に行われます。 更新プログラムのロールアウトが近づくにつれて、 [Microsoft 365 メッセージセンター](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)を経由して通知されます。

> [!NOTE]
> [管理センター](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)を使用してメッセージセンターにアクセスするには、Microsoft 365 または Azure AD アカウントが必要です。 Microsoft 365 home プランユーザーには管理センターがありません。


## <a name="standard-release"></a>標準リリース

これは、ユーザーがすべてのお客様に幅広くリリースされている場合に最新の更新プログラムを受信する既定のオプションです。
  
ユーザーの大部分を**標準のリリース**と IT プロフェッショナルおよびパワーユーザーに任せて、新しい機能を評価し、ビジネスユーザーと役員をサポートするチームを**準備すること**をお勧めします。 
  
> [!NOTE]
> 対象指定リリースから標準リリースに切り替えた場合、ユーザーは標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。 
  
## <a name="targeted-release"></a>対象となるリリース

このオプションでは、お客様とお客様のユーザーは最新の更新プログラムを先に確認できて、早い時点でフィードバックをすることで製品像の決定に協力できます。更新プログラムを個人で早く受信するか、組織全体で早く受信するかを選ぶことができます。
  
> [!IMPORTANT]
> 大規模な更新プログラムまたは複雑な更新プログラムは、悪影響を受けるユーザーがいないようにするために他の更新プログラムに比べて時間がかかる場合があります。 リリースは、予定どおりになる保証はありません。 
  
### <a name="targeted-release-for-entire-organization"></a>組織全体の対象指定リリース

このオプションに対して[管理センターでリリースオプションを設定](#set-up-the-release-option-in-the-admin-center)すると、すべてのユーザーが対象となるリリースの手順を取得できます。 ユーザー数が 300 を超える組織では、このオプションにテスト サブスクリプションを使用することをお勧めします。 テスト サブスクリプションについては、Microsoft の担当者にお問い合わせください。 
  
### <a name="targeted-release-for-selected-users"></a>選択したユーザーの対象指定リリース

このオプションに対して[管理センターでリリースオプションを設定](#set-up-the-release-option-in-the-admin-center)した場合は、特定のユーザー (通常は power users) を定義して、機能に早期にアクセスできるようにすることができます。 
  
## <a name="benefits-of-targeted-release"></a>対象指定リリースの利点

対象指定リリースでは、管理者、変更マネージャー、または Microsoft 365 更新プログラムを担当するその他のユーザーに、次のことを許可することにより、今後の変更を準備することができます。
  
- 組織内のすべてのユーザーにリリースされる前に、新しい更新プログラムをテストおよび検証する。
    
- 更新プログラムが全世界でリリースされる前に、ユーザー通知およびドキュメントを準備する。
    
- 今後の変更に関する社内ヘルプ デスクを準備する。
    
- コンプライアンスとセキュリティ レビューに合格する。
    
- 機能制御を必要に応じて使用して、エンド ユーザーに対する更新プログラムのリリースを制御する。
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>管理センターでリリースオプションを設定する

次の手順に従って、組織が Microsoft 365 の更新プログラムを受信する方法を変更できます。 オプトインするには、Microsoft 365 のグローバル管理者である必要があります。
  
> [!IMPORTANT]
> 以下の変更が Microsoft 365 で有効になるまで、最大24時間かかる場合があります。 対象指定リリースをいったん有効にした後に無効にすると、予定された標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。 
  
1. 管理センターで、[**設定**] [組織  >  **設定**] に移動し、[**組織プロファイル**] タブの [**リリース環境設定**] を選択します。

5. 対象指定リリースを無効にするには、[ **Standard release**] を選択し、[**変更の保存**] を選択します。 
    
6. 組織内のすべてのユーザーに対して対象指定リリースを有効にするには、[すべて**のユーザーに対象**とするリリース] を選択し、[**変更の保存**] を選択します。 
    
7. 組織内の一部のユーザーに対して対象指定リリースを有効にするには、[**選択したユーザーの対象指定リリース**] を選択し、[**変更の保存**] を選択します。 
    
8. 一度に1人のユーザーを追加する場合は **[ユーザーを選択**する] を選択し、ユーザーを一括して追加する場合は [**アップロード**] を選択します。
    
9. ユーザーの追加が完了したら、[**変更の保存**] を選択します。


  
## <a name="learn-more"></a>詳細情報

[Microsoft 365 メッセージセンター](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)の[メッセージを管理](https://docs.microsoft.com/office365/admin/manage/message-center)して、今後の microsoft 365 の更新プログラムとリリースに関する通知を取得する方法について説明します。
