---
title: Microsoft セキュア スコア
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、どのようにセキュリティ体制を改善するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
keywords: microsoft secure score、secure score、office 365 のセキュリティスコア、microsoft セキュリティスコア、microsoft 365 セキュリティセンター、改善アクション
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: a41e05f54a8ba94752c6df91628a2200367ac0f3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843842"
---
# <a name="microsoft-secure-score"></a>Microsoft セキュア スコア

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。 この点については https://security.microsoft.com/securescore 、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。

セキュリティで保護されたスコアの推奨事項に従うことで、組織を脅威から保護することができます。 Microsoft 365 セキュリティ センターの集中管理されたダッシュボードから、組織の Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視し、操作することができます。

セキュア スコアは、次のような方法で組織の役に立ちます。  

* 組織のセキュリティ体制の現在の状態について報告します。
* 検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。  
* ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。

指標と傾向の堅牢な視覚化、他の Microsoft 製品との統合、類似組織とのスコア比較などを、組織で利用することができます。 スコアは、サードパーティのソリューションが推奨アクションに対応した場合も反映されます。

![セキュリティで保護されたスコアホームページ](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>メカニズム

ここでは、次のアクションのポイントを指定します。

- 推奨されるセキュリティ機能を構成する
- セキュリティ関連タスクの実行
- サードパーティ製のアプリケーションまたはソフトウェア、または別の対策を使用した改善アクションへの対応

一部の改善アクションでは、完全に完了した時点のみが指定できます。 一部のデバイスまたはユーザーについては、一部のポイントを部分的に指定します。 改善アクションの1つを実行できない、または実行する必要がない場合は、リスクまたは残存リスクを受け入れるかどうかを選択できます。

サポートされているいずれかの Microsoft 製品のライセンスを所有している場合は、これらの製品に関する推奨事項が表示されます。 ライセンスエディション、サブスクリプション、またはプランに関係なく、製品に対して提供される機能強化の完全なセットについて説明します。 これにより、セキュリティ上のベストプラクティスを理解し、スコアを向上させることができます。 セキュリティで保護されたスコアで表される絶対的なセキュリティに関する姿勢は、組織が特定の製品についてどのライセンスを所有しているかにかかわらず変わりません。 セキュリティは使いやすさとバランスが取れている必要があり、すべての推奨事項がご使用の環境に適しているわけではないことを覚えておいてください。

スコアはリアルタイムで更新され、視覚エフェクト ページと改善のための処置 ページに表示された情報を反映します。 またセキュア スコアは毎日同期を行い、各アクションで達成されたポイントに関するシステム データを受信します。

### <a name="key-scenarios"></a>重要なシナリオ

- [現在のスコアを確認する](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [自分のスコアを組織と同じように比較する](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [改善アクションを表示し、アクションプランを決定する](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [調査または実装のための作業フローの開始](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 セキュリティセンターと ServiceNow 統合](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>改善のための処置のスコア

各改善アクションは、10ポイント以下の価値があり、ほとんどはバイナリ形式でスコアされます。 [改善] アクションを実装して、新しいポリシーを作成したり、特定の設定を有効にしたりすると、ポイントの100% が得られます。 その他の改善のための処置では、ポイントは構成全体に対するパーセンテージに応じて与えられます。

たとえば、改善アクションによって、多要素認証を使用するすべてのユーザーを保護することで、10ポイントが得られることが示されます。 保護されているユーザー100の総数は50のみで、5ポイント (50 保護/100 合計 * 10、最大ポイント5ポイント) の部分的なスコアを取得します。

### <a name="products-included-in-secure-score"></a>セキュア スコアに含まれる製品

現時点では、Microsoft 365 (Exchange Online)、Azure Active Directory、Microsoft Defender for Endpoint、microsoft Defender for Identity、および Cloud App Security に関する推奨事項があります。 その他のセキュリティ製品の推奨事項は近日リリース予定です。 推奨事項は、各製品に関連付けられているすべての攻撃対象を網羅しているわけではありませんが、適切な基準になっています。 また、強化された機能をサードパーティの対象としてマークしたり、別の軽減対策にマークしたりすることもできます。

### <a name="security-defaults"></a>セキュリティの既定値

Microsoft のセキュリティで保護されたスコア [では、Azure Active Directory のセキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートするように改善アクションが更新されているため、一般的な攻撃に対して構成済みのセキュリティ設定を使用して組織を保護することが容易になります

[セキュリティの既定] をオンにすると、次の強化された操作について完全なポイントが与えられます。

- すべてのユーザーが、セキュリティで保護されたアクセスに対して多要素認証を完了できるようにする (9 ポイント)
- 管理役割に MFA を必要とする (10 ポイント)
- 従来の認証をブロックするポリシーを有効にする (7 ポイント)

>[!IMPORTANT]
>セキュリティの既定値には、「サインインリスクポリシー」と「ユーザーリスクポリシー」の強化アクションに似たセキュリティを提供するセキュリティ機能が含まれます。 これらのポリシーをセキュリティの既定の設定の上で設定する代わりに、それぞれの状態を "代替対策によって解決されました" に更新することをお勧めします。

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

読み取り専用アクセスでは、改善アクションの状態やメモを編集したり、スコア領域を編集したり、カスタム比較を編集したりすることはできません。

* ヘルプデスク管理者
* ユーザー管理者
* サービス管理者
* セキュリティ閲覧者
* セキュリティ オペレーター
* グローバル閲覧者

## <a name="risk-awareness"></a>リスク認識

Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティについての数値の概要です。 これは、システムやデータが侵害される可能性の絶対的な測定値ではありません。 そうではなく、侵害されるリスクを相殺できるように、Microsoft 環境にセキュリティコントロールを採用している範囲を表しています。 セキュリティ侵害の対象となるオンラインサービスは一切なく、セキュリティ違反に対する保証としては、どのような方法でも安全なスコアを保証しないようにする必要があります。

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティ」に投稿してお知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
- [新機能](microsoft-secure-score-whats-new.md)
