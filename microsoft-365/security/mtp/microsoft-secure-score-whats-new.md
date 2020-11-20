---
title: Microsoft セキュリティスコアの新機能
description: Microsoft 365 セキュリティセンターの Microsoft セキュリティスコアに対して発生した新しい変更点について説明します。
keywords: microsoft secure score、セキュリティスコア、office 365 のセキュリティスコア、microsoft セキュリティスコア、microsoft 365 セキュリティセンター
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
ms.openlocfilehash: 0ba3d7a5e46f7e0f8677ce2844c5551bf70739e3
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367115"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft セキュリティスコアの新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft のセキュリティの評価をより良いものにするには、いくつかの変更を行いました。 予定されている変更の詳細については、「 [Microsoft Secure Score の内容](microsoft-secure-score-whats-coming.md)」を参照してください。

## <a name="november-2020"></a>2020 年 11 月

### <a name="added-3-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>エンドポイント (以前の Microsoft Defender ATP) に関する Microsoft Defender のサービス関連の改善アクションを3つ追加しました。

- Windows サービスの引用符で囲まれるサービスパスを修正する
- サービスの実行可能パスを共通の保護された場所に変更する
- Windows レジストリでパスワードがキャッシュされないようにサービスアカウントを変更する

## <a name="october-2020"></a>2020 年 10 月

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>エンドポイントの Microsoft Defender に関連する向上アクションを削除する

- Microsoft Defender SmartScreen Windows ストアアプリの web コンテンツチェックを設定して警告を発する

## <a name="august-2020"></a>2020 年 8 月

### <a name="updated-improvement-action-for-azure-active-directory"></a>Azure Active Directory の改善アクションを更新しました

- レガシ認証をブロックするポリシーを有効にする

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Id のセキュリティで保護されたスコアとグラフ API の非互換性

Microsoft Secure Score の最近のリリースでは、向上したスコアリングモデルがリリースされました。 これらの変更により、より柔軟かつ正確にセキュリティ状況を表示することができます。 しかし、これらの更新プログラムにより、Microsoft セキュリティスコアが Id のセキュリティで保護されたスコアと Graph API とは一時的に互換性がなくなりました。

時間では、Id のセキュリティスコアと Graph API が新しいスコアリングモデルを採用します。 その後、Microsoft のセキュリティで保護されたスコア、Id のセキュリティで保護されたスコア、Graph API によって報告されたスコアの違いがわかります。 ご不便をかけて申し訳ございません。今後、このようなエクスペリエンスの互換性を確保するために取り組んでいます。

## <a name="updated-improvement-actions"></a>更新された改善アクション

- Azure Active Directory の改善アクションを追加しました
- Id の改善アクションのために Microsoft Defender を追加しました
- エンドポイントの脅威に対する Microsoft Defender のサポート [& 脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) のセキュリティに関する推奨事項
    - リリースされた TVM で提供されるすべてのセキュリティの推奨事項を使用できるようになりました。

## <a name="updated-interface-and-functionality"></a>更新されたインターフェイスと機能

* CISO およびリード レベルのディスカッションのすべての新しい指標と傾向の表示
* スコアを追跡して評価するための新しい方法
* スコア回帰の追跡と理解の向上
* 改善のための処置のフィルタリング、タグ付け、検索、グループ化
* スコア予測と計画されているアクションを使用して、将来の目標に向けて管理する
* その他多数。

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、「 [Security, Privacy & コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティ」に投稿してお知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
