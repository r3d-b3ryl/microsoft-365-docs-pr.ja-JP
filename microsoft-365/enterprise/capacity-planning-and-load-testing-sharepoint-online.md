---
title: SharePoint Online のキャパシティ プランニングとロード テスト
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: この記事では、許可されないので、従来SharePointを実行せずにオンラインに展開する方法について説明します。
ms.openlocfilehash: fb54864168b35fed290ccb1139cb6c607969820d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216074"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>SharePoint Online のキャパシティ プランニングとロード テスト
この記事では、従来の負荷テストを行わずに SharePoint Online に展開する方法について説明します。この方法は、オンラインでは読み込みテストがSharePointです。 SharePointオンラインはクラウド サービスであり、サービスの負荷機能、正常性、および全体的な負荷のバランスは Microsoft によって管理されます。
  
サイトを起動する成功を確実にするための最善の方法は、ポータルの起動ロールアウトの計画で強調されている基本的な原則、プラクティス、推奨事項に [従う方法です](planportallaunchroll-out.md)。

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>オンラインで容量計画SharePoint実行する方法の概要 
オンプレミス展開に対する SharePoint Online の主な利点の 1 つは、クラウドの弾力性と、分散地域のユーザーの最適化です。 当社の大規模な環境は、毎日何百万人ものユーザーにサービスを提供するために設定されています。そのため、ファームのバランスを取り、拡大することで容量を効果的に処理することが重要です。
  
多くの場合、1 つのファーム内の 1 つのテナントの増加は予測できませんが、要求の集計合計は時間の間に予測可能です。 オンラインの成長傾向をSharePoint、今後の拡大を計画できます。
  
容量を効率的に使用し、予期しない成長に対処するために、どのファームでも、サービスのさまざまな要素を追跡および監視するオートメーションがあります。 複数のメトリックが使用され、主要なメトリックの 1 つが CPU 負荷になります。これは、フロントエンド サーバーをスケールアップするシグナルとして使用されます。 さらに、SQL 環境は負荷と時間の増加に応じて拡張され、フェーズとウェーブに従ってその負荷と成長の正しい分布が可能になりますので、段階的[/](planportallaunchroll-out.md)波のアプローチをお勧めします。 

容量は、継続的にハードウェアを追加するだけでなく、有効な負荷要求にサービスを提供するためにその容量を管理および制御する方法にも関係します。 お客様が最適なエクスペリエンスを得る方法を確認するために、推奨されるガイダンスに従ってお客様をお勧めします。 また、サービスで "虐待的な" 動作を許可しない調整パターンとコントロールが用意されています。 すべての "悪い" 動作が意図的な動作ではない一方で、その動作の影響を制限する必要があります。 調整の詳細と回避方法については、「調整を回避する方法」のガイダンス記事 [を参照](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) してください。

## <a name="why-you-cannot-load-test-sharepoint-online"></a>オンラインでテスト を読み込SharePoint理由
オンプレミス環境では、負荷テストを使用してスケールの仮定を検証し、最終的にはファームのブレークポイントを見つける。負荷で飽和状態に設定します。 

オンラインSharePointでは、スケールが比較的流動的で、特定のヒューリスティックに基づいて負荷を調整、制御する必要があります。 このような大規模なマルチテナント環境なので、同じファーム内のすべてのテナントを保護する必要があります。そのため、負荷テストは自動的に調整されます。 ただし、調整を行う以外に、テストを読み込もうとすると、スケールとファームのバランス調整アクションがオンオンに行われるため、今日テストしたファームは、テスト期間中またはテスト後数時間以内にスケール変更があった可能性が高いので、残念で誤解を招く可能性のある結果を受け取ります。

サービスとしてテスト SharePointを読み込もうとするのではなく、推奨されるプラクティスに従い、「作成、起動、および正常なポータル ガイダンスの維持」に[従](/sharepoint/portal-health)ってください。