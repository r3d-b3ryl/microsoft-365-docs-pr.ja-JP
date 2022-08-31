---
title: Microsoft Secure Score の新機能
description: Microsoft 365 Defender ポータルで Microsoft Secure Score に対して行った新しい変更について説明します。
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, Microsoft 365 Defender portal
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.openlocfilehash: e5bea982a1cbc776a9529532bbbac4da4199fb4a
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482584"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Microsoft Secure Score の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score をセキュリティ体制をより適切に表すために、引き続き新機能と改善アクションを追加します。

より多くの改善アクションを実行すればするほど、セキュリティ スコアは高くなります。 詳細については、 [Microsoft セキュリティ スコア](microsoft-secure-score.md)に関するページを参照してください。

Microsoft Secure Score は<https://security.microsoft.com/securescore>[、Microsoft 365 Defender ポータル](microsoft-365-defender-portal.md)にあります。

## <a name="august-2022"></a>2022 年 8 月

新しいMicrosoft Information Protectionの推奨事項は、セキュア スコアの改善アクションとして使用できるようになりました。

- **ラベル付け**
  - Azure Purview データ マップの資産に M365 秘密度ラベル付けを拡張する
  - 自動ラベル付けデータ分類ポリシーが設定され、使用されていることを確認する
  - M365 秘密度ラベル データ分類ポリシーを公開する
  - データ損失防止 (DLP) ポリシーを作成する

新しいMicrosoft Defender for Office 365の推奨事項は、セキュリティスコア改善アクションとして使用できるようになりました。

- **スパム対策 - 受信ポリシー**
  - 電子メール一括苦情レベル (BCL) のしきい値を 6 以下に設定する
  - スパム検出に対して実行するアクションを設定する
  - 信頼度の高いスパム検出に対して実行するアクションを設定する
  - フィッシングの検出に対して実行するアクションを設定する
  - 信頼度の高いフィッシング検出を実行するアクションを設定する
  - 一括スパム検出で実行するアクションを設定する
  - 検疫でスパムを 30 日間保持する
  - スパムの安全性に関するヒントが有効になっていることを確認する
  - スパム対策ポリシーに対して送信者ドメインが許可されていないことを確認します ("スパム対策ポリシーで許可されている送信者ドメインがないことを確認する" と置き換えて、特定の送信者に対しても機能を拡張します)

- **スパム対策 - 送信ポリシー**
  - ユーザーが 1 時間あたりに電子メールで送信できる外部受信者の最大数を設定する
  - ユーザーが 1 時間以内に送信できる内部受信者の最大数を設定する
  - 1 日のメッセージ制限を設定する
  - メッセージの制限に達したユーザーをブロックする
  - 自動メール転送ルールをシステム制御に設定する

- **スパム対策 - 接続フィルター**
  - 接続フィルター ポリシーに許可された IP アドレスを追加しない

## <a name="june-2022"></a>2022 年 6 月

- 新しいMicrosoft Defender for EndpointとMicrosoft Defender 脆弱性の管理の推奨事項は、セキュア スコアの改善アクションとして使用できるようになりました。

  - 共有へのオフライン アクセスを禁止する
  - 共有書き込みアクセス許可セットを **すべてのユーザー** に削除する
  - ルート フォルダーから共有を削除する
  - 共有のフォルダー アクセス ベースの列挙を設定する
  - コア コンポーネントMicrosoft Defender for Endpoint更新する

- セキュリティスコアの改善アクションとして、新しいMicrosoft Defender for Identity推奨事項を利用できます。

  - セキュリティで保護されていないドメイン構成を解決する

- 新しい [アプリ ガバナンス](/defender-cloud-apps/app-governance-manage-app-governance) の推奨事項が、セキュア スコアの改善アクションとして利用できるようになりました。

  - 優先度アカウントからの同意を得てアプリを規制する

- 新しい Salesforce と ServiceNow の推奨事項は、Microsoft Defender for Cloud Apps顧客向けのセキュリティスコア改善アクションとして利用できるようになりました。 詳細については、「 [SaaS セキュリティ体制管理の概要」を](https://aka.ms/saas_security_posture_management)参照してください。

> [!NOTE]
> Salesforce コントロールと ServiceNow コントロールがパブリック プレビューで使用できるようになりました。

## <a name="april-2022"></a>2022 年 4 月

- リモート接続のユーザー認証を有効にする

## <a name="december-2021"></a>2021 年 12 月

- ブロック モードで安全な添付ファイルを有効にする
- 外部ユーザー Exchange Online予定表の詳細を共有できないようにする
- Office クライアントの安全なドキュメントを有効にする
- マルウェア対策ポリシーの一般的な添付ファイル フィルター設定を有効にする
- スパム対策ポリシーに許可されている送信者ドメインがないことを確認する
- 電子メール メッセージの安全なリンク ポリシーを作成する
- マルウェアのゼロ時間自動消去ポリシーを作成する
- SharePoint、OneDrive、Microsoft Teams でMicrosoft Defender for Office 365を有効にする
- フィッシング メッセージのゼロ時間自動消去ポリシーを作成する
- スパム メッセージのゼロ時間自動消去ポリシーを作成する
- 悪用された脆弱な署名されたドライバーの悪用をブロックする
- フル スキャン中にリムーバブル ドライブのスキャンを有効にする

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

問題がある場合は、 [セキュリティ、プライバシー、コンプライアンス](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) コミュニティに投稿&お知らせください。 コミュニティを監視しているので、問題に対応します。

## <a name="related-resources"></a>関連リソース

- [セキュリティ体制にアクセス](microsoft-secure-score-improvement-actions.md)
- [Microsoft Secure Score 履歴を追跡し、目標を達成する](microsoft-secure-score-history-metrics-trends.md)
- [今後の予定](microsoft-secure-score-whats-coming.md)
