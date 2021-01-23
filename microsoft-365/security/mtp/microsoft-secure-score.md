---
title: Microsoft セキュア スコア
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、どのようにセキュリティ体制を改善するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
keywords: Microsoft セキュア スコア, セキュア スコア, Office 365 セキュア スコア, Microsoft セキュリティ スコア, Microsoft 365 セキュリティ センター, 改善アクション
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 39abcbde82c2902b091b42db3dbc8e1ee2cbd924
ms.sourcegitcommit: 8b3ff6e9f8931327b6f0541fd882107687cd123e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2021
ms.locfileid: "49942792"
---
# <a name="microsoft-secure-score"></a>Microsoft セキュア スコア

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。 https://security.microsoft.com/securescore[これは、Microsoft 365](overview-security-center.md)セキュリティ センターにあります。

セキュリティ スコアの推奨事項に従って、組織を脅威から保護できます。 Microsoft 365 セキュリティ センターの一元的なダッシュボードから、組織は Microsoft 365 の ID、アプリ、デバイスのセキュリティを監視し、作業できます。

セキュア スコアは、次のような方法で組織の役に立ちます。  

* 組織のセキュリティ体制の現在の状態について報告します。
* 検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。  
* ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。

指標と傾向の堅牢な視覚化、他の Microsoft 製品との統合、類似組織とのスコア比較などを、組織で利用することができます。 スコアは、サードパーティのソリューションが推奨アクションに対応した場合も反映されます。

![セキュア スコア ホームページ](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>メカニズム

次のアクションのポイントが与えられる。

- 推奨されるセキュリティ機能の構成
- セキュリティ関連のタスクを実行する
- サード パーティ製のアプリケーションまたはソフトウェア、または代替の軽減策を使用して改善アクションに対処する

一部の改善アクションは、完全に完了した時点でのみポイントを与える場合があります。 一部のデバイスまたはユーザーに対して完了した場合、部分的にポイントを与える場合があります。 改善アクションの 1 つを実行できない場合、または実行しない場合は、リスクまたは残存リスクを受け入れるか選択できます。

サポートされている Microsoft 製品の 1 つのライセンスを持っている場合は、それらの製品に関する推奨事項が表示されます。 ライセンスのエディション、サブスクリプション、プランに関係なく、製品に対して可能な一連の改善点が表示されます。 これにより、セキュリティのベスト プラクティスを理解し、スコアを向上できます。 セキュリティ スコアで表される絶対的なセキュリティ体制は、組織が特定の製品に対して所有するライセンスに関係なく同じままです。 セキュリティは使いやすさとバランスが取れている必要があり、すべての推奨事項がご使用の環境に適しているわけではないことを覚えておいてください。

スコアはリアルタイムで更新され、視覚エフェクト ページと改善のための処置 ページに表示された情報を反映します。 またセキュア スコアは毎日同期を行い、各アクションで達成されたポイントに関するシステム データを受信します。

### <a name="key-scenarios"></a>重要なシナリオ

- [現在のスコアを確認する](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [スコアを自分のような組織と比較する](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [改善アクションを表示し、アクション プランを決定する](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [調査または実装するためのワーク フローの開始](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>改善のための処置のスコア

各改善アクションは 10 ポイント以下の価値を持ち、そのほとんどはバイナリ形式でスコア付けされます。 新しいポリシーの作成や特定の設定のオンなど、改善アクションを実装すると、ポイントの 100% が取得されます。 その他の改善のための処置では、ポイントは構成全体に対するパーセンテージに応じて与えられます。

たとえば、改善アクションでは、多要素認証を使用してすべてのユーザーを保護することで 10 ポイントを取得できます。 保護されているユーザーの総数は 100 人中 50 人だけなので、部分的なスコアは 5 ポイント (50 保護 / 100 合計 * 10 最大 pts = 5 pts) になります。

### <a name="products-included-in-secure-score"></a>セキュア スコアに含まれる製品

現在、次の製品に関する推奨事項があります。

- Microsoft 365 (Exchange Online を含む)
- Azure Active Directory
- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Cloud App Security
- Microsoft Teams

その他のセキュリティ製品の推奨事項は近日リリース予定です。 推奨事項は、各製品に関連付けられているすべての攻撃表面をカバーしているのではなく、優れたベースラインです。 また、改善アクションをサード パーティまたは代替の軽減策の対象としてマークできます。

### <a name="security-defaults"></a>セキュリティの既定値

Microsoft セキュア スコアは [、Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)のセキュリティの既定値をサポートするように改善アクションを更新しました。これは、一般的な攻撃に対して事前に構成されたセキュリティ設定を使用して組織を簡単に保護するのに役立ちます。

セキュリティの既定値を有効にした場合、次の改善のためのすべてのポイントが与されます。

- すべてのユーザーがセキュリティで保護されたアクセスのための多要素認証を完了できる (9 ポイント)
- 管理者ロールに MFA を要求する (10 ポイント)
- 従来の認証をブロックするポリシーを有効にする (7 ポイント)

>[!IMPORTANT]
>セキュリティの既定値には、"サインイン リスク ポリシー" および "ユーザー リスク ポリシー" の改善アクションと同様のセキュリティを提供するセキュリティ機能が含まれます。 これらのポリシーをセキュリティの既定値の上に設定する代わりに、状態を 「代替の軽減策で解決」に更新することをお勧めします。

## <a name="required-permissions"></a>必要なアクセス許可

Microsoft セキュア スコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory で次のいずれかの役割が割り当てられている必要があります。

### <a name="read-and-write-roles"></a>読み取りと書き込みの役割

読み取りと書き込みアクセス許可があれば、変更を加えたり、セキュア スコアを直接操作したりできます。 他のユーザーに読み取り専用アクセス権を割り当てることもできます。

* グローバル管理者
* セキュリティ管理者
* Exchange 管理者
* SharePoint 管理者
* アカウント管理者

### <a name="read-only-roles"></a>読み取り専用の役割

読み取り専用アクセスでは、改善アクションの状態やメモを編集したり、スコア ゾーンを編集したり、カスタム比較を編集したりできない。

* ヘルプデスク管理者
* ユーザー管理者
* サービス管理者
* セキュリティ閲覧者
* セキュリティ オペレーター
* グローバル閲覧者

## <a name="risk-awareness"></a>リスク認識

Microsoft セキュア スコアは、システム構成、ユーザーの動作、その他のセキュリティ関連の測定値に基づく、セキュリティ体制の数値の要約です。 これは、システムまたはデータが侵害される可能性を絶対に測定する方法ではない。 これは、侵害のリスクを軽減するために役立つ、Microsoft 環境でどの程度のセキュリティ制御を採用したのかという点を表しています。 どのオンライン サービスもセキュリティ違反の影響を受け、セキュリティ スコアはセキュリティ違反に対する保証とは解釈されません。

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、セキュリティ/プライバシー/コンプライアンス コミュニティに投稿して [&知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) らせてください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [Microsoft セキュア スコアの履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
- [新機能](microsoft-secure-score-whats-new.md)
