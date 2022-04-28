---
title: SharePoint Online のキャパシティ プランニングとロード テスト
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
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
description: この記事では、従来のロード テストを実行せずにSharePoint Online にデプロイする方法について説明します。これは許可されていないためです。
ms.openlocfilehash: 1d1714bbcdefdbc41ff3ac5d038c6b59a7043a26
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65101097"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>SharePoint Online のキャパシティ プランニングとロード テスト
この記事では、SharePoint Online ではロード テストが許可されていないため、従来のロード テストなしで SharePoint Online にデプロイする方法について説明します。 SharePoint Online はクラウド サービスであり、サービスの負荷機能、正常性、および負荷の全体的なバランスは Microsoft によって管理されます。
  
サイトの起動を成功させるための最善の方法は、ポータルの起動 [ロールアウト計画](planportallaunchroll-out.md)で強調表示されている基本的な原則、プラクティス、および推奨事項に従う方法です。

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>SharePoint Online で容量計画を実行する方法の概要 
オンプレミスのデプロイに対する SharePoint Online の主な利点の 1 つは、クラウドの弾力性と分散リージョン内のユーザーの最適化です。 大規模な環境は、毎日数百万人のユーザーにサービスを提供するように設定されているため、ファームのバランスと拡張によって容量を効果的に処理することが重要です。
  
多くの場合、任意の 1 つのファーム内の 1 つのテナントでは増加は予測できませんが、集計された要求の合計は時間の経過と共に予測可能です。 SharePoint Online の成長傾向を特定することで、将来の拡張を計画できます。
  
容量を効率的に使用し、予期しない成長に対処するために、どのファームでも、サービスのさまざまな要素を追跡および監視する自動化があります。 複数のメトリックが利用され、主要なメトリックの 1 つが CPU 負荷であり、フロントエンド サーバーをスケールアップするためのシグナルとして使用されます。 さらに、時間の経過と共にSQL環境は負荷と増加に応じてスケーリングされ、フェーズとウェーブに従うとその負荷と増加が正しく分散されるため、[段階的/ウェーブ](planportallaunchroll-out.md)アプローチをお勧めします。 

容量は、継続的にハードウェアを追加するだけでなく、有効な負荷要求にサービスを提供するために、その容量を管理および制御することにも関係します。 お客様が最適なエクスペリエンスを得られるように、推奨されるガイダンスに従うことをお勧めします。 また、サービスで "不正な" 動作を許可しないように調整パターンと制御が用意されていることも意味します。 すべての "悪い" 動作が意図的であるとは限りませんが、その動作の効果を確実に制限する必要があります。 調整とそれを回避する方法の詳細については、調整されるの [を回避する方法に関するガイダンス](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) に関する記事を参照してください。

## <a name="why-you-cannot-load-test-sharepoint-online"></a>オンラインでロード テストSharePointできない理由
オンプレミス環境では、ロード テストを使用してスケールの前提条件を検証し、最終的にファームのブレークポイントを見つけます。読み込みで飽和状態にすることで、次の処理を行います。 

SharePoint Online では、スケールが比較的流動的であり、特定のヒューリスティックに基づいて負荷が調整、調整、制御されるため、異なる方法で行う必要があります。 このような大規模なマルチテナント環境であるため、同じファーム内のすべてのテナントを保護する必要があるため、ロード テストはすべて自動的に調整されます。 ただし、ロード テストを試みると、調整される以外に、今日テストしたファームは、スケールとファームのバランス調整アクションが継続的に実行されるため、テスト期間中またはテスト後数時間以内にスケール変更が発生した可能性があるため、残念で誤解を招く可能性のある結果が得られます。

サービスとしてSharePointをロード テストするのではなく、推奨されるプラクティスに従い[、正常なポータルガイダンスの作成、起動、および保守](/sharepoint/portal-health)に従ってください。