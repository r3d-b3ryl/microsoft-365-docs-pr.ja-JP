---
title: Microsoft Secure Score の新機能
description: セキュリティ センターの Microsoft Secure Score に加えた新しい変更Microsoft 365説明します。
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: c0abdd26456fe9c7d2ee6111f8c15805af3f66b7738b42ee79fb1a230e08239d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53884141"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft Secure Score の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score をセキュリティの姿勢をより良くするために、いくつかの変更を加えた。 今後の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score-whats-coming.md)」を参照してください。

Microsoft Secure Score は、セキュリティ https://security.microsoft.com/securescore センターのMicrosoft 365[にあります](overview-security-center.md)。

## <a name="july-2021"></a>2021 年 7 月

### <a name="added-improvement-action-related-to-microsoft-teams"></a>アプリに関連する改善アクションをMicrosoft Teams

- ダイヤルイン ユーザーによる会議ロビーのバイパスを制限する
- 外部参加者が会議で制御を行Teamsする
- 匿名ユーザーによる会議の開始Teams制限する
- 会議に対してロビーをセットアップTeamsする
- 会議に参加できるユーザーをTeamsする

### <a name="added-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint に関連する改善アクションを追加しました

- MacOS 用の Microsoft Defender for Endpoint センサー データ収集を修正する
- MacOS の Microsoft Defender for Endpoint 障害のある通信を修正する
- macOS でパスワードの最小長を 15 文字以上に設定する
- macOS で 'パスワード履歴を強制する' を '24 以上のパスワード' に設定する
- macOS で '最大パスワード期間' を '90 以下の日数に設定するが、0 には設定しない]
- macOS でアカウントロックアウトのしきい値を 5 以下に設定する
- macOS でファイアウォールを有効にする
- ゲートキーパーを有効にする
- システム整合性保護 (SIP) を有効にする
- FileVault ディスク暗号化を有効にする
- macOS でスクリーンセーバーが起動するときに画面をロックする
- macOS でスクリーンセーバーが 20 分以下で開始する設定を確認する
- ホーム フォルダーのセキュリティ保護
- macOS のMicrosoft Defender ウイルス対策保護を有効にする
- macOS のMicrosoft Defender ウイルス対策 PUA 保護を有効にする
- macOS Microsoft Defender ウイルス対策クラウドによる保護を有効にする
- macOS Microsoft Defender ウイルス対策定義を更新する
- Microsoft Defender for Endpoint sensor data collection for Linux の修正
- Linux 用の Microsoft Defender for Endpoint 障害のある通信を修正する
- 制限されていないアクセス アカウント
- Linux のMicrosoft Defender ウイルス対策保護を有効にする
- Linux のブロック Microsoft Defender ウイルス対策 PUA 保護を有効にする
- Linux Microsoft Defender ウイルス対策クラウドによる保護を有効にする
- Linux Microsoft Defender ウイルス対策定義を更新する

## <a name="june-2021"></a>2021 年 6 月

### <a name="removed-improvement-action-related-to-microsoft-cloud-app-security"></a>ユーザーに関連する改善アクションをMicrosoft Cloud App Security

- 異常なCloud App Securityを検出するには、次の情報を使用します。

## <a name="february-2021"></a>2021年2月

### <a name="compatibility-with-graph-api"></a>API とのGraph互換性

Microsoft Secure Score の推奨事項は、Graph API を介して配信され、セキュリティ センターで現在表示されている推奨事項と同じようにMicrosoft 365されます。

## <a name="january-2021"></a>2021 年 1 月

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>セキュリティに関する最初の推奨事項を追加Microsoft Teams

Microsoft Teamsユーザーは、Secure Score の新しい改善アクションとして「匿名ユーザーの会議への参加を制限する」と表示されます。

## <a name="december-2020"></a>2020 年 12 月

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint に 6 つのアカウント関連の改善アクションを追加しました。

- '最小パスワード長' を '14 文字以上' に設定する
- [パスワード履歴の適用] を [24 以上のパスワード] に設定する
- [パスワードの最大保存期間] を [60 日以下] に設定しますが、0 には設定できません。
- [最小パスワードの使用時間] を [1 日以上] に設定する
- 組み込みの管理者アカウントを無効にする
- 組み込みのゲスト アカウントを無効にする

## <a name="november-2020"></a>2020 年 11 月

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>Secure Score を使用して ServiceNow チケットを作成する機能が削除されました 

[ServiceNow の共有] にアクセスして Secure Score を使用して **ServiceNow チケット** >作成する機能は使用できなくなりました。 次の手順を決定する間、フィードバックと継続的なサポートに感謝します。

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint に 3 つのサービス関連の改善アクションを追加しました。

- サービスの引用されていないサービス パスをWindowsする
- サービスの実行可能パスを共通の保護された場所に変更する
- Windows レジストリにキャッシュされたパスワードを回避するためにサービス アカウントを変更する

## <a name="october-2020"></a>2020 年 10 月

### <a name="removed-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint に関連する改善アクションを削除しました

- ストア Microsoft Defender SmartScreen Windows Web コンテンツ チェックを警告に設定する

## <a name="august-2020"></a>2020 年 8 月

### <a name="updated-improvement-action-for-azure-active-directory"></a>ユーザーの改善アクションを更新Azure Active Directory

- レガシ認証をブロックするポリシーを有効にする

## <a name="incompatibility-with-identity-secure-score"></a>Identity Secure Score との非互換性

Microsoft Secure Score の最近のリリースでは、スコアリング モデルが改善されました。 これらの変更により、セキュリティの態勢をより柔軟かつ正確に把握できます。 ただし、これらの更新プログラムにより、Microsoft Secure Score は一時的に Identity Secure Score と互換性がありません。

時間内に、Identity Secure Score は新しいスコアリング モデルを採用します。 それまでは、Microsoft Secure Score と Identity Secure Score によって報告されたスコアの違いが表示されます。 ご不便をおかけして申し訳ございませんが、今後、これらのエクスペリエンスの互換性を確保するために取り組み中です。

## <a name="updated-improvement-actions"></a>更新された改善アクション

- 改善Azure Active Directory追加
- Microsoft Defender for Identity の改善アクションを追加しました
- Microsoft Defender for Endpoint [Threat &のセキュリティ](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) 推奨事項のサポート
    - TVM によって提供されるリリース済みセキュリティ推奨事項が利用可能にな

## <a name="updated-interface-and-functionality"></a>インターフェイスと機能の更新

* CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示
* スコアを追跡して評価するための新しい方法
* スコア回帰の追跡と理解の向上
* 改善のための処置のフィルタリング、タグ付け、検索、グループ化
* スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する
* その他多数。

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、セキュリティ、プライバシー、コンプライアンス コミュニティに投稿して [&してください](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) 。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [Microsoft Secure Score の履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
