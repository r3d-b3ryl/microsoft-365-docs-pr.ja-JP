---
title: 標準リリースオプションまたはターゲット リリース オプションを設定する
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: 新しい製品と機能の更新プログラムのリリース オプションを設定する方法については、Microsoft 365 管理センター。
ms.openlocfilehash: c9a3478c15ad5505bae73b6821fc8ed9511f9b3e
ms.sourcegitcommit: 38a07b23d41763275628ab89e2e4e58ae2926997
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58346786"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>標準リリースオプションまたはターゲット リリース オプションを設定する

> [!IMPORTANT]
> このMicrosoft 365の更新プログラムは、オンライン、オンライン、およびMicrosoft 365、SharePointに適用Exchange Online。 これらのリリース オプションは、Microsoft 365に対する変更をリリースするための最善の努力の方法ですが、すべての時間またはすべての更新プログラムについて保証することはできません。 これらのサービスは、Microsoft 365 Apps、Skype for Business、Microsoft Teamsには適用されません。 リリース オプションの詳細については、「Microsoft 365 Appsの更新プログラム チャネルの概要」[を参照Microsoft 365 Apps。](/deployoffice/overview-update-channels)

このMicrosoft 365、数年ごとにコストの高い更新プログラムを実行する代わりに、新しい製品の更新プログラムと機能が利用できると受け取る必要があります。 組織がこれらの更新プログラムを受け取る方法を管理できます。 たとえば、組織が最初に更新プログラムを受け取る前に、早期リリースにサインアップできます。 特定の個人だけが更新プログラムを受け取る方法を指定できます。 または、既定のリリース スケジュールのままで、後で更新プログラムを受信することもできます。 この記事では、さまざまなリリース オプションと、それらを組織で使用する方法について説明します。

## <a name="how-it-works---release-validation"></a>しくみ - リリースの検証

すべての新しいリリースは、最初に機能チームによってテストされ、検証され、次に、Microsoft 365機能チーム全体が、その後に Microsoft のすべてによって検証されます。 内部テストと検証が終わったら、次の手順は参加しているお客様に向けた **対象指定リリース** (以前は先行リリースと呼ばれていました) です。 各リリース リングで、Microsoft はフィードバックを収集し、主要な利用状況メトリックを監視することでさらに品質を検証します。 この革新的な一連の検証は、全世界のリリースの信頼性を最大限に高めるためにあります。 各リリースを、次の図で示します。 
  
![ユーザーの検証リングを解放Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
重要な更新プログラムの場合、お客様は最初はロードマップによって[Microsoft 365されます](https://products.office.com/business/office-365-roadmap)。 更新プログラムが展開に近づくにつれて、メッセージ センターからMicrosoft 365[されます](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)。

> [!NOTE]
> 管理センターからMicrosoft 365メッセージ センター ADアクセスするには、管理者アカウントまたは Azure アカウントが[必要です](/office365/admin/admin-overview/about-the-admin-center)。 Microsoft 365ユーザーに管理センターが設定されていない場合。


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

対象のリリースでは、管理者、変更マネージャー、または更新プログラムを担当する他Microsoft 365、次の変更に備えて、次の情報を提供できます。
  
- 組織内のすべてのユーザーにリリースされる前に、新しい更新プログラムをテストおよび検証する。
    
- 更新プログラムが全世界でリリースされる前に、ユーザー通知およびドキュメントを準備する。
    
- 今後の変更に関する社内ヘルプ デスクを準備する。
    
- コンプライアンスとセキュリティ レビューに合格する。
    
- 機能制御を必要に応じて使用して、エンド ユーザーに対する更新プログラムのリリースを制御する。
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>管理センターでリリース オプションを設定する

次の手順に従って、組織Microsoft 365更新プログラムを受け取る方法を変更できます。 オプトインを行う場合は、Microsoft 365管理者である必要があります。
  
> [!IMPORTANT]
> 以下の変更が適用される場合は、最大で 24 時間かかる場合Microsoft 365。 対象指定リリースをいったん有効にした後に無効にすると、予定された標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。 
  
1. 管理センターで、[組織の設定]の [組織設定] に移動し、[組織プロファイル] タブの [基本設定のリリース  >  ]<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank"></a>**を選択します**。

5. 対象リリースを無効にするには、[標準リリース] **を選択し**、[変更の保存] **を選択します**。 
    
6. 組織内のすべてのユーザーの対象リリースを有効にするには、[すべてのユーザーの対象リリース] を選択し、[変更の保存]**を選択します**。 
    
7. 組織内の一部のユーザーの対象リリースを有効にするには、[選択したユーザーの対象リリース] を選択し、[変更の保存]**を選択します**。 
    
8. [**ユーザーを一度** に 1 人追加するユーザーを選択する] を選択するか、アップロード **ユーザー** を一括で追加します。
    
9. ユーザーの追加が完了したら、[変更の保存] **を選択します**。
  
## <a name="next-steps"></a>次の手順

メッセージ センターで[メッセージ](/office365/admin/manage/message-center)を管理して、Microsoft 365[更新](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)プログラムとリリースに関する通知Microsoft 365確認します。

## <a name="related-content"></a>関連コンテンツ

[インサイダー プログラムOffice参加する](https://insider.office.com/join/windows)(記事)
