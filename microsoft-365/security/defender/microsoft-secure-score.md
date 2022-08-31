---
title: Microsoft セキュア スコア
description: Microsoft 365 Defender ポータルでの Microsoft セキュリティ スコア、セキュリティ体制の改善方法、およびセキュリティ管理者が期待できる内容について説明します。
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, Microsoft 365 Defender portal, 改善アクション
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- Adm_TOC
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 2e4618644860cf1f5370749e65d2d8bcb5aca8a0
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480276"
---
# <a name="microsoft-secure-score"></a>Microsoft セキュア スコア

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft セキュア スコアは組織のセキュリティ体制を測定する数値であり、数値が高いほどより多くの改善のための処置が実行されたことを示しています。 https://security.microsoft.com/securescore [Microsoft 365 Defender ポータル](microsoft-365-defender-portal.md)にあります。

セキュリティ スコアの推奨事項を実行することにより、組織を脅威から保護できます。 組織は、Microsoft 365 Defender ポータルの一元化されたダッシュボードから、Microsoft 365 ID、アプリ、デバイスのセキュリティを監視および操作できます。

セキュア スコアは、次のような方法で組織の役に立ちます。  

* 組織のセキュリティ体制の現在の状態について報告します。
* 検出可能性、可視性、ガイダンス、制御機能を提供して、セキュリティ体制を改善します。  
* ベンチマークと比較し、主要業績評価指標 (KPI) を確立します。

セキュア スコアの概要については、このビデオをご覧ください。
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWUPrP]

指標と傾向の堅牢な視覚化、他の Microsoft 製品との統合、類似組織とのスコア比較などを、組織で利用することができます。 スコアは、サードパーティのソリューションが推奨アクションに対応した場合も反映されます。

:::image type="content" source="../../media/secure-score/secure-score-home-page.png" alt-text="Microsoft 365 Defender ポータルの Microsoft Secure Score ホームページ" lightbox="../../media/secure-score/secure-score-home-page.png":::

## <a name="how-it-works"></a>メカニズム

次のアクションのポイントが与えられます。

- 推奨されるセキュリティ機能の構成
- セキュリティ関連のタスクの実行
- サード パーティ製のアプリケーションまたはソフトウェア、または代替の軽減策を使用して改善アクションに対処する

一部の改善アクションでは、完全に完了した場合にのみポイントが付与されます。 一部のデバイスまたはユーザーに対して完了した場合、部分的なポイントを与えるものもあります。 改善アクションの 1 つを実行できない場合、または実行しない場合は、リスクまたは残りのリスクを受け入れることを選択できます。

サポートされているいずれかの Microsoft 製品のライセンスをお持ちであれば、それらの製品に関する推奨事項が表示されます。 ライセンスのエディション、サブスクリプション、またはプランに関係なく、製品に対して可能な改善の完全なセットが表示されます。 こうすることで、セキュリティのベスト プラクティスを理解し、スコアを向上させることができます。 セキュリティ スコアで表される絶対的なセキュリティ体制は、組織が特定の製品に対して所有しているライセンスに関係なく、同じままです。 セキュリティは使いやすさとバランスが取れている必要があり、すべての推奨事項がご使用の環境に適しているわけではないことを覚えておいてください。

スコアはリアルタイムで更新され、視覚エフェクト ページと改善のための処置 ページに表示された情報を反映します。 またセキュア スコアは毎日同期を行い、各アクションで達成されたポイントに関するシステム データを受信します。

### <a name="key-scenarios"></a>重要なシナリオ

- [現在のスコアを確認する](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [スコアを自分のような組織と比較する](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [改善アクションを表示し、アクション プランを決定する](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [調査または実装する作業フローを開始する](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>改善のための処置のスコア

各改善アクションは 10 ポイント以下の価値があり、ほとんどがバイナリ形式でスコア付けされます。 新しいポリシーの作成や特定の設定のオンなど、改善アクションを実装すると、ポイントの 100% が得られます。 その他の改善のための処置では、ポイントは構成全体に対するパーセンテージに応じて与えられます。

たとえば、改善アクションでは、多要素認証ですべてのユーザーを保護することで 10 ポイントを取得します。 ユーザーの合計が 100 人中 50 人しか保護されていないため、5 ポイント (50 保護/ 100 合計 * 10 max pts = 5 pts) の部分スコアが得られます。

### <a name="products-included-in-secure-score"></a>セキュア スコアに含まれる製品

現在、次の製品に関する推奨事項があります。

- Microsoft 365 (Exchange Onlineを含む)
- Azure Active Directory
- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Defender for Cloud Apps
- Microsoft Teams

その他のセキュリティ製品の推奨事項は近日リリース予定です。 推奨事項は、各製品に関連付けられているすべての攻撃面をカバーするわけではありませんが、適切なベースラインです。 また、サード パーティまたは代替の軽減策の対象として改善アクションをマークすることもできます。

### <a name="security-defaults"></a>セキュリティの既定値

Microsoft Secure Score は、 [Azure Active Directory のセキュリティの既定値](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)をサポートするように改善アクションを更新しました。これにより、一般的な攻撃に対して事前に構成されたセキュリティ設定で組織を保護しやすくなります。

セキュリティの既定値を有効にすると、次の改善アクションに対して完全なポイントが付与されます。

- すべてのユーザーがセキュリティで保護されたアクセスのために多要素認証を完了できることを確認する (9 ポイント)
- 管理ロールに MFA を要求する (10 ポイント)
- 従来の認証をブロックするポリシーを有効にする (7 ポイント)

>[!IMPORTANT]
>セキュリティの既定値には、"サインイン リスク ポリシー" と "ユーザー リスク ポリシー" の改善アクションと同様のセキュリティを提供するセキュリティ機能が含まれます。 セキュリティの既定値に基づいてこれらのポリシーを設定する代わりに、状態を "別の軽減策で解決済み" に更新することをお勧めします。

## <a name="required-permissions"></a>必要なアクセス許可

Microsoft セキュア スコアにアクセスするためのアクセス許可を付与するには、Azure Active Directory で次のいずれかの役割が割り当てられている必要があります。

### <a name="read-and-write-roles"></a>読み取りと書き込みの役割

読み取りと書き込みアクセス許可があれば、変更を加えたり、セキュア スコアを直接操作したりできます。 他のユーザーに読み取り専用アクセス権を割り当てることもできます。

* グローバル管理者
* セキュリティ管理者
* Exchange 管理者
* SharePoint 管理者

### <a name="read-only-roles"></a>読み取り専用の役割

読み取り専用アクセスでは、改善アクションの状態やメモの編集、スコア ゾーンの編集、カスタム比較の編集を行うことはできません。

* ヘルプデスク管理者
* ユーザー管理者
* サービス サポート管理者
* セキュリティ閲覧者
* セキュリティ オペレーター
* グローバル閲覧者

## <a name="risk-awareness"></a>リスク認識

Microsoft Secure Score は、システム構成、ユーザーの動作、およびその他のセキュリティ関連の測定値に基づいて、セキュリティ体制の数値的な概要です。 システムまたはデータが侵害される可能性を絶対的に測定するわけではありません。 これは、侵害されるリスクを軽減するのに役立つ、Microsoft 環境でセキュリティ制御を採用した範囲を表します。 セキュリティ侵害の影響を受けないオンライン サービスはありません。セキュリティ スコアは、いかなる方法でもセキュリティ違反に対する保証として解釈されるべきではありません。

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、 [セキュリティ、プライバシー、コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿&お知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [Microsoft Secure Score 履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
- [新機能](microsoft-secure-score-whats-new.md)
