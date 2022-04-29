---
title: Standard または Targeted リリース オプションを設定する
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Microsoft 365 管理センターで新しい製品と機能の更新プログラムのリリース オプションを設定する方法について説明します。
ms.openlocfilehash: 176558448f31fadea0b0cf865bca5d1156e3eefe
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65129422"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a>Standard または Targeted リリース オプションを設定する

> [!IMPORTANT]
> この記事で説明するMicrosoft 365更新プログラムは、Microsoft 365、SharePoint Online、およびExchange Onlineに適用されます。 これらのリリース オプションは、Microsoft 365に対する変更をリリースするためのベスト エフォート型の方法を対象としていますが、常に、またはすべての更新プログラムについて保証することはできません。 Microsoft 365 Apps、Skype for Business、Microsoft Teams、および関連サービスには適用されません。 Microsoft 365 Appsのリリース オプションの詳細については、「[Microsoft 365 Appsの更新チャネルの概要」を](/deployoffice/overview-update-channels)参照してください。

Microsoft 365では、数年ごとにコストのかかる更新プログラムを実行する代わりに、新しい製品の更新プログラムと機能が利用可能になります。 組織でこれらの更新プログラムを受け取る方法を管理できます。 たとえば、組織が最初に更新プログラムを受信するように、早期リリースにサインアップできます。 特定のユーザーのみが更新プログラムを受信することを指定できます。 または、既定のリリース スケジュールのままで、後で更新プログラムを受け取ることもできます。 この記事では、さまざまなリリース オプションと、組織で使用する方法について説明します。

## <a name="how-it-works---release-validation"></a>しくみ - リリースの検証

すべての新しいリリースは、最初に機能チームによってテストされ、検証され、次にMicrosoft 365機能チーム全体がテストされ、検証され、その後に Microsoft がすべてテストされます。 内部テストと検証が終わったら、次の手順は参加しているお客様に向けた **対象指定リリース** (以前は先行リリースと呼ばれていました) です。 各リリース リングで、Microsoft はフィードバックを収集し、主要な利用状況メトリックを監視することでさらに品質を検証します。 この革新的な一連の検証は、全世界のリリースの信頼性を最大限に高めるためにあります。 各リリースを、次の図で示します。 
  
![Microsoft 365の検証リングをリリースします。](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
重要な更新プログラムの場合、お客様は最初に[Microsoft 365ロードマップ](https://products.office.com/business/office-365-roadmap)から通知を受け取ります。 更新プログラムがロールアウトに近づくにつれて、[Microsoft 365 メッセージ センター](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)を通じて通信されます。

> [!NOTE]
> [管理センター](/office365/admin/admin-overview/admin-center-overview)からメッセージ センターにアクセスするには、Microsoft 365またはAzure ADアカウントが必要です。 Microsoft 365ホーム プランのユーザーには管理センターがありません。

## <a name="standard-release"></a>標準リリース

これは、すべての顧客に広くリリースされたときに、ユーザーとユーザーが最新の更新プログラムを受け取る既定のオプションです。
  
良い方法は、 **Standard リリース** と IT 担当者の大半のユーザーを **ターゲット リリース** に残して、新機能を評価し、ビジネス ユーザーや経営陣をサポートするチームを準備することです。 
  
> [!NOTE]
> 対象指定リリースから標準リリースに切り替えた場合、ユーザーは標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。 
  
## <a name="targeted-release"></a>対象となるリリース

このオプションでは、お客様とお客様のユーザーは最新の更新プログラムを先に確認できて、早い時点でフィードバックをすることで製品像の決定に協力できます。更新プログラムを個人で早く受信するか、組織全体で早く受信するかを選ぶことができます。
  
> [!IMPORTANT]
> - 大規模な更新プログラムまたは複雑な更新プログラムは、悪影響を受けるユーザーがいないようにするために他の更新プログラムに比べて時間がかかる場合があります。 リリースは、予定どおりになる保証はありません。
> - 現在、対象となるリリースは、Office 365 GCC プランまたは Office 365 GCC High プランと DoD プランをお持ちのお客様にはご利用いただけません。
  
### <a name="targeted-release-for-entire-organization"></a>組織全体の対象指定リリース

この [オプションの管理センターでリリース オプションを設定](#set-up-the-release-option-in-the-admin-center) すると、すべてのユーザーが対象リリース エクスペリエンスを利用できるようになります。 ユーザー数が 300 を超える組織では、このオプションにテスト サブスクリプションを使用することをお勧めします。 テスト サブスクリプションについては、Microsoft の担当者にお問い合わせください。 
  
### <a name="targeted-release-for-selected-users"></a>選択したユーザーの対象指定リリース

この [オプションの管理センターでリリース オプションを設定](#set-up-the-release-option-in-the-admin-center) する場合は、特定のユーザー (通常は電源ユーザー) を定義して、機能と機能への早期アクセスを受け取ることができます。

> [!IMPORTANT]
> 一部の機能は、組織単位でのみロールアウトされます。 つまり、組織全体が機能へのアクセスを同時に受け取ります。 このような機能の場合、対象となるリリース プログラムで選択したユーザーが早期に機能を取得することはできません。 つまり、対象となるリリースで選択したユーザーを構成した場合、組織は早期にこれらの機能を受け取ることができません。 対象となるリリースのすべての機能が確実に表示されるようにするには、組織全体の対象となるリリースを構成するか、テスト組織を設定する必要があります。
  
## <a name="benefits-of-targeted-release"></a>対象指定リリースの利点

対象となるリリースを使用すると、管理者、変更マネージャー、またはMicrosoft 365更新を担当する他のユーザーは、次のことを許可することで、今後の変更に備えます。
  
- 組織内のすべてのユーザーにリリースされる前に、新しい更新プログラムをテストおよび検証する。
    
- 更新プログラムが全世界でリリースされる前に、ユーザー通知およびドキュメントを準備する。
    
- 今後の変更に関する社内ヘルプ デスクを準備する。
    
- コンプライアンスとセキュリティ レビューに合格する。
    
- 機能制御を必要に応じて使用して、エンド ユーザーに対する更新プログラムのリリースを制御する。
    
## <a name="set-up-the-release-option-in-the-admin-center"></a>管理センターでリリース オプションを設定する

次の手順に従って、組織がMicrosoft 365更新プログラムを受け取る方法を変更できます。 オプトインするには、Microsoft 365のグローバル管理者である必要があります。
  
> [!IMPORTANT]
> 以下の変更がMicrosoft 365で有効になるまでには、最大で 24 時間かかる場合があります。 対象指定リリースをいったん有効にした後に無効にすると、予定された標準リリースにまだ到達していない機能にアクセスできなくなる可能性があります。 
  
1. 管理センターの **[設定** > **Org 設定]** に移動し、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2067339" target="_blank">**組織プロファイル**] タブの [</a>**リリース設定**] を選択します。

5. 対象のリリースを無効にするには、[ **標準リリース**] を選択し、[ **変更の保存**] を選択します。 
    
6. 組織内のすべてのユーザーに対してターゲット リリースを有効にするには、 **すべてのユーザーに対して [ターゲット リリース**] を選択し、[ **変更の保存]** を選択します。 
    
7. 組織内の一部のユーザーの対象となるリリースを有効にするには、 **選択したユーザーの対象となるリリース** を選択し、[ **変更の保存]** を選択します。 
    
8. [**ユーザーの選択] を選択** してユーザーを 1 つずつ追加するか、**ユーザーを一** 括で追加アップロードします。
    
9. ユーザーの追加が完了したら、[変更の **保存]** を選択します。
  
## <a name="next-steps"></a>次の手順

[Microsoft 365 メッセージ センター](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)で[メッセージを管理](/office365/admin/manage/message-center)して、今後のMicrosoft 365更新プログラムとリリースに関する通知を取得する方法について説明します。

## <a name="related-content"></a>関連コンテンツ

[Office Insider Program に参加](https://insider.office.com/join/windows)する (記事)
