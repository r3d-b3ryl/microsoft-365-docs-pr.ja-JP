---
title: Microsoft セキュア スコア
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、どのようにセキュリティ体制を改善するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュア スコア、セキュリティ センター、改善のための処置
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
ms.openlocfilehash: 862a25eddda6048349df937641914377cb25874f
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200040"
---
# <a name="microsoft-secure-score"></a>Microsoft セキュア スコア

Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。 この点については https://security.microsoft.com/securescore 、「 [Microsoft 365 セキュリティセンター](overview-security-center.md)」を参照してください。

セキュリティで保護されたスコアの推奨事項に従うことで、組織を脅威から保護することができます。 Microsoft 365 セキュリティ センターの集中管理されたダッシュボードから、組織の Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視し、操作することができます。

セキュア スコアは、次のような方法で組織の役に立ちます。  

* 組織のセキュリティ体制の現在の状態について報告します。
* 検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。  
* ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。

指標と傾向の堅牢な視覚化、他の Microsoft 製品との統合、類似組織とのスコア比較などを、組織で利用することができます。 スコアは、サードパーティのソリューションが推奨アクションに対応した場合も反映されます。

![セキュリティで保護されたスコアホームページ](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>メカニズム

推奨されるセキュリティ機能の構成、セキュリティ関連タスクの実行、またはサードパーティ製のアプリケーションまたはソフトウェアを使用した改善アクションへの対処、または別の軽減対策を行うためのポイントが提供されています。 改善のための処置の中には、完全に完了したときにのみポイントが与えられるものがあります。また、一部のデバイスやユーザーにより完了された場合に、ポイントの一部が加えられるものもあります。 改善アクションのいずれかを実行できない、または適用したくない場合は、リスクを受け入れるか、リスクを軽減することを選択できます。

サポートされているいずれかの Microsoft 製品のライセンスを所有している場合は、これらの製品に関する推奨事項が表示されます。 セキュリティ上のベストプラクティスを理解し、スコアを向上させるために、ライセンスエディション、サブスクリプション、またはプランに関係なく、製品に提供される機能強化の完全なセットを示しています。 セキュリティの絶対的な姿勢は、セキュリティで保護されたスコアで表されます。これは、組織が特定の製品についてどのライセンスを所有しているかにかかわらず変わりません。 セキュリティは使いやすさとバランスが取れている必要があり、すべての推奨事項がご使用の環境に適しているわけではないことを覚えておいてください。

スコアはリアルタイムで更新され、視覚エフェクト ページと改善のための処置 ページに表示された情報を反映します。 またセキュア スコアは毎日同期を行い、各アクションで達成されたポイントに関するシステム データを受信します。

### <a name="key-scenarios"></a>重要なシナリオ

- [現在のスコアを確認する](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [自分のスコアを組織と同じように比較する](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [改善アクションを表示し、アクションプランを決定する](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [調査または実装のための作業フローの開始](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 セキュリティセンターと ServiceNow 統合](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>改善のための処置のスコア

各改善アクションには、10ポイント以下の価値があります。 多くの場合、スコアはバイナリ方式で獲得されます。新しいポリシーを作成したり、特定の設定を有効にしたりするなど、改善のための処置を実装すると、ポイントの 100% が得られます。 その他の改善のための処置では、ポイントは構成全体に対するパーセンテージに応じて与えられます。 たとえば、強化アクションによって、多要素認証を使用するすべてのユーザーを保護することにより、すべて100のユーザーを保護することによって10ポイント獲得した場合に、保護されているユーザーの合計数が50の場合は、5ポイント (50 保護/100 合計 * 10 最大 pts = 5 ポイント部分スコア) になります。

### <a name="products-included-in-secure-score"></a>セキュア スコアに含まれる製品

現在、Microsoft 365 (Exchange Online を含む)、Azure AD、Microsoft Defender ATP、Azure ATP、および Cloud App Security に関する推奨事項があります。 その他のセキュリティ製品の推奨事項は近日リリース予定です。 推奨事項は、各製品に関連付けられているすべての攻撃対象を網羅するわけではありませんが、適切な基準になります。 また、強化された機能をサードパーティの対象としてマークしたり、別の軽減対策にマークしたりすることもできます。

### <a name="security-defaults"></a>セキュリティの既定値

Microsoft のセキュリティで保護されたスコア[では、Azure Active Directory のセキュリティの既定](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートするように改善アクションが更新されているため、一般的な攻撃に対して構成済みのセキュリティ設定を使用して組織を保護することが容易になります

[セキュリティの既定] をオンにすると、次の強化されたアクションについて完全なポイントが付与されます。

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

読み取り専用アクセス許可があっても、改善のための処置のステータスやメモの編集、スコア ゾーンの編集、カスタム比較の編集を行うことはできません。

* ヘルプデスク管理者
* ユーザー管理者
* サービス管理者
* セキュリティ閲覧者
* セキュリティ オペレーター
* グローバル閲覧者

## <a name="risk-awareness"></a>リスク認識

Microsoft Secure Score は、システム構成、ユーザーの行動、およびその他のセキュリティ関連の測定値に基づいて、セキュリティの状況を示す数値の概要です。システムまたはデータが侵害される可能性の絶対的な測定値ではありません。 むしろ、それは Microsoft 環境にセキュリティ制御を適用した範囲を表します。これは、侵害のリスクを相殺するのに役立ちます。 オンライン サービスをセキュリティ侵害から完全に保護することはできません。いかなる仕方でも、セキュア スコアをセキュリティ侵害に対する保証として解釈するべきではありません。

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、[Security, Privacy & Compliance](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿してお知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [セキュリティの姿勢を評価する](microsoft-secure-score-improvement-actions.md)
- [Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
- [新機能](microsoft-secure-score-whats-new.md)
