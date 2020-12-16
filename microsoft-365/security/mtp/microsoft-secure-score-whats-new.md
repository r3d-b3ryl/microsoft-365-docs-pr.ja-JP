---
title: Microsoft セキュア スコアの新機能
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアに加えた新しい変更について説明します。
keywords: Microsoft セキュア スコア、セキュア スコア、Office 365 セキュア スコア、Microsoft セキュリティ スコア、Microsoft 365 セキュリティ センター
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
ms.openlocfilehash: 253e85da7bb85a0722831851f00051a50a96153e
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688413"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft セキュア スコアの新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft セキュア スコアをセキュリティの立ち上がりをより良くするために、いくつかの変更が加えらたのです。 今後の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score-whats-coming.md)」を参照してください。

Microsoft セキュア スコアは https://security.microsoft.com/securescore [、Microsoft 365](overview-security-center.md)セキュリティ センターにあります。

## <a name="december-2020"></a>2020年12月

### <a name="added-6-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Microsoft Defender for Endpoint (以前の Microsoft Defender ATP) に、アカウント関連の改善のためのアクションを 6 つ追加しました。

- [パスワードの最小文字数] を 「14 文字以上」に設定する
- [パスワード履歴の適用] を [24 以上のパスワード] に設定する
- [パスワードの最大保存期間] を [60 日以下に設定しますが、0 日に設定しない] に設定します。
- [パスワードの最小保存時間] を [1 日以上] に設定する
- 組み込みの Administrator アカウントを無効にする
- 組み込みのゲスト アカウントを無効にする

## <a name="november-2020"></a>2020 年 11 月

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>セキュア スコアを使用して ServiceNow チケットを作成する機能が削除されました 

ServiceNow の共有にアクセスしてセキュア スコアを使用して ServiceNow **チケット>** 作成する機能は使用できなくなりました。 次の手順を決定する間、フィードバックと継続的なサポートに感謝します。

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Microsoft Defender for Endpoint (以前の Microsoft Defender ATP) に 3 つのサービス関連の改善アクションを追加しました。

- Windows サービスのクォートされていないサービス パスを修正する
- サービスの実行可能パスを共通の保護された場所に変更する
- Windows レジストリにキャッシュされたパスワードを回避するためにサービス アカウントを変更する

## <a name="october-2020"></a>2020 年 10 月

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint に関連する改善アクションを削除する

- Microsoft Defender SmartScreen Windows ストア アプリの Web コンテンツ チェックで警告を表示する設定

## <a name="august-2020"></a>2020 年 8 月

### <a name="updated-improvement-action-for-azure-active-directory"></a>Azure Active Directory の改善アクションの更新

- レガシ認証をブロックするポリシーを有効にする

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>ID セキュア スコアおよび Graph API との互換性

Microsoft セキュア スコアの最近のリリースでは、スコアモデルが改善されました。 これらの変更により、セキュリティの状況をより柔軟かつ正確に把握できます。 ただし、これらの更新により、Microsoft セキュア スコアは一時的に Id セキュア スコアおよび Graph API と互換性がありません。

時間がたつ間に、Id セキュア スコアと Graph API は新しいスコアモデルを採用します。 それまでは、Microsoft セキュア スコア、ID セキュア スコア、および Graph API によって報告されるスコアの違いが表示されます。 ご不便をおかけして申し訳ございません。今後、これらのエクスペリエンスの互換性を確保するために取り組み中です。

## <a name="updated-improvement-actions"></a>改善アクションの更新

- Azure Active Directory 改善アクションを追加しました
- Id 向上のための Microsoft Defender アクションを追加しました
- 脆弱性管理のセキュリティに関 [する推奨事項& Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Defender for Endpoint Threat のサポート
    - TVM によって提供されるリリース済みセキュリティに関する推奨事項すべてが使用可能に

## <a name="updated-interface-and-functionality"></a>インターフェイスと機能の更新

* CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示
* スコアを追跡して評価するための新しい方法
* スコア回帰の追跡と理解の向上
* 改善のための処置のフィルタリング、タグ付け、検索、グループ化
* スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する
* その他多数。

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、セキュリティ/プライバシー/コンプライアンス コミュニティに投稿して [&知](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) らせてください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [Microsoft セキュア スコアの履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
