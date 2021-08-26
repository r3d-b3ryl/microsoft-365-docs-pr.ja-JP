---
title: Microsoft Defender for Office 365 の新機能
description: Microsoft Defender for Office 365 の最新リリースで利用できる新機能について説明します。
keywords: Microsoft Defender for Office 365、ga、一般提供、機能、利用可能、新しい
search.appverid: met150
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.date: 07/27/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae01a929121488399ac3a016f0b33ae7b28ff96d
ms.sourcegitcommit: 6c342a956b2dbc32be33bac1a23a5038490f1b40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58533617"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

この記事では、Microsoft Defender for microsoft Defender の最新リリースの新機能をOffice 365。 現在プレビュー中の機能は (プレビュー) **で示されます**。

[このビデオ](https://www.youtube.com/watch?v=Tdz6KfruDGo&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=3)を見て詳細をご確認ください。

> [!TIP]
> Microsoft Defender for Office 365ありませんか? [試用版を開始するために販売に問い合わせ。](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)

## <a name="august-2021"></a>2021 年 8 月

- [報告されたメッセージの管理レビュー](admin-review-reported-message.md): 管理者は、報告されたメッセージを確認した後、テンプレートメッセージをエンド ユーザーに送り返す機能を持つ。 これは、組織に合わせてカスタマイズし、管理者の評決にも基づいてカスタマイズできます。 
=======
## <a name="september-2021"></a>2021 年 9 月

- [検疫ポリシー](quarantine-policies.md): 管理者は、検疫済みメッセージへの受信者アクセスの詳細な制御を構成し、エンドユーザーのスパム通知をカスタマイズできます。
  - [管理者エクスペリエンスのビデオ](https://youtu.be/vnar4HowfpY)
  - [エンド ユーザー エクスペリエンスのビデオ](https://youtu.be/s-vozLO43rI)
  - 検疫エクスペリエンスに追加されるその他の新機能については、このブログ記事「検疫エクスペリエンスの簡素化」 [で説明します](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/simplifying-the-quarantine-experience/ba-p/2676388)。

## <a name="august-2021"></a>2021 年 8 月

- [報告されたメッセージの管理レビュー](admin-review-reported-message.md): 管理者は、報告されたメッセージを確認した後、テンプレートメッセージをエンド ユーザーに送り返す機能を持つ。 テンプレートは、組織に合わせてカスタマイズし、管理者の評決にも基づいてカスタマイズできます。
- [[テナント許可/](manage-tenant-allows.md)ブロック一覧に許可を追加する] : ブロックされたメッセージが管理者申請プロセスの一部として送信された場合に、許可エントリをテナント許可/ブロックリストに追加できます。 ブロックの性質に応じて、送信された URL、ファイル、送信者の許可がテナント許可/ブロック一覧に追加されます。 ほとんどの場合、許可はシステムに時間を与え、保証されている場合は自然に許可するために追加されます。 場合によっては、Microsoft が許可を管理します。

## <a name="july-2021"></a>2021 年 7 月

- [自動調査における電子メール分析の改善](email-analysis-investigations.md)
- [高度な](configure-advanced-delivery.md)配信: ユーザーへのサード パーティのフィッシング シミュレーションの配信とセキュリティ操作メールボックスへのフィルター処理されていないメッセージの配信を構成するための新しい機能を導入します。
- [セーフサイトのリンクMicrosoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams)
- 次のシナリオの新しいアラート ポリシー: 侵害されたメールボックス、フォームフィッシング、上書きおよび ZAP の切り上がりにより配信される悪意のあるメール
  - 疑わしいメール転送アクティビティ
  - フォームの共有と応答の収集を制限されたユーザー
  - フィッシング詐欺の可能性が原因でフォームがブロックされる
  - フォームにフラグが設定され、フィッシングとして確認される
  - [ZAP の新しいアラート ポリシー](../../compliance/new-defender-alert-policies.md)
- Microsoft Defender for Office 365アラートは、統合アラート キューと統合Microsoft 365 Defenderおよび統合Microsoft 365 Defenderキュー[に統合されました](../defender/investigate-alerts.md)
- [](user-tags.md)ユーザー タグは、Office 365 セキュリティ & コンプライアンスのアラート キューと詳細、ユーザー タグへのカスタム アラート ポリシーのスコープ設定など、Office 365 アラート エクスペリエンスのために Microsoft Defender に統合され、対象となるアラート ポリシーを作成できます。 
  - タグは、Microsoft 365 Defender センターの統合アラート キューでも使用できます (Microsoft Defender for Office 365 プラン 2)

## <a name="june-2021"></a>2021 年 6 月

- フィッシング対策ポリシー内安全性のヒントの連絡先と連絡先の新しい設定。 この安全性のヒントは、受信者が最初に送信者からメールを受信するか、送信者からメールを受信しない場合に表示されます。 この設定と構成方法の詳細については、次の記事を参照してください。
  - [最初の連絡先安全性のヒント](set-up-anti-phishing-policies.md#first-contact-safety-tip)
  - [EOP でのスパム対策ポリシーの構成](configure-anti-phishing-policies-eop.md)
  - [Microsoft Defender でフィッシング対策ポリシーを構成Office 365](configure-mdo-anti-phishing-policies.md)

## <a name="aprilmay-2021"></a>2021 年 4 月/5 月

- [[電子メール](mdo-email-entity-page.md)エンティティ] ページ : 脅威、認証と検出、発発の詳細、および新しい電子メール プレビュー エクスペリエンスに関する情報が充実した電子メールの統合された 360 度ビュー。
- [Office 365管理 API](/office/office-365-management-api/office-365-management-activity-api-schema#email-message-events): 配信アクション、元の配信場所と最新の配信場所、および更新された検出の詳細を追加する EmailEvents (RecordType 28) の更新。
- [脅威分析 for Defender for Office 365](/microsoft-365/security/defender/threat-analytics): アクティブな脅威アクター、一般的な手法、攻撃表面を表示し、進行中のキャンペーンに関する Microsoft の研究者からの広範な報告を表示します。

## <a name="februarymarch-2021"></a>2021 年 2 月/3 月

- 検索エクスペリエンスでのアラート ID の統合 (アラート ID とAlert-Explorerナビゲーションを使用[した検索](threat-explorer.md))
- 狩猟エクスペリエンスでのレコードのエクスポートの制限を 9990 から 200,000 に [増やす](threat-explorer.md)
- 試用版テナントのエクスプローラー (およびリアルタイム検出) データの保持と検索の制限を 7 (前の制限) から 30 日間のハンティング エクスペリエンス [に拡張する](threat-explorer.md)
- 保護されたユーザーまたはドメインに対する偽装攻撃を検索するための、エクスプローラー内の偽装ドメインと偽装ユーザー (およびリアルタイムの検出) と呼ばれる新しい検索ピボット。 詳細については、「詳細」を [参照してください](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains)。 (Microsoft Defender for Office 365プラン 1 またはプラン 2)

## <a name="december-2020"></a>2020 年 12 月

- [既定ではセキュリティで保護Office 365](secure-by-default.md)
- 自動調査の機能強化: 手動でトリガーされた電子メール調査に関する一般的なアラート、メールボックスの変更を別のエンティティ カテゴリとして扱い、冗長な URL ブロック アクションを削除し、ユーザーが侵害された調査のために送信メール クラスターを作成します。

## <a name="november-2020"></a>2020 年 11 月

- Review > アクション センター >メール送信とアクション ログからの修復のエクスポート制限を更新しました (Defender for Office 365 プラン 2)

## <a name="septemberoctober-2020"></a>2020 年 9 月/10 月

- 新しい最初の連絡先安全性のヒント、受信者が最初に送信者から電子メールを受信するか、送信者から電子メールを受信しない場合に使用されます。 この設定の詳細と、メール フロー ルール (トランスポート ルールとも呼Exchange) を使用して構成する方法については[、「First contact](set-up-anti-phishing-policies.md#first-contact-safety-tip)安全性のヒント」 を参照してください。
- [Configuration Analyzer を使用してポリシーを確認する](configuration-analyzer-for-security-policies.md)
- トップ ターゲットユーザー、トランスポート ルール、コネクタを含む脅威エクスプローラーの拡張機能[(Threat](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) [Explorer](threat-explorer.md)の Office 365 の Defender 情報 (テナント/ユーザー ポリシーによって電子メールが許可/ブロックされました) (Defender for Office 365 Plan 2)
- 脅威エクスプローラー (マルウェア、フィッシング、スパム、またはなし) で URL の脅威を検出する[(Defender](threat-explorer.md#threats-in-urls) for Office 365 プラン 2)
- [脅威、追加アクション](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming)、配信場所、および更新されたタイムライン ビューに関する更新プログラムを含むハンティング エクスペリエンス脅威エクスプローラーの機能強化 (Defender for Office 365 プラン 2)

## <a name="julyaugust-2020"></a>2020 年 7 月/8 月

- [ハンティング エクスペリエンスの改善点](threat-explorer.md#improvements-to-threat-hunting-experience)(Microsoft Defender for Office 365プラン 1 またはプラン 2)
- [事前設定されたセキュリティ ポリシーを使用して推奨設定を簡単に適用する](preset-security-policies.md)

## <a name="marchapril-2020"></a>2020 年 3 月/4 月

- 調査と対応 [を自動化](address-compromised-users-quickly.md) して、侵害されたユーザー アカウントに対処する機能が一般に利用可能になります。 (Microsoft Defender for Office 365プラン 2)

## <a name="januaryfebruary-2020"></a>2020 年 1 月/2 月

- [Microsoft Defender for microsoft Defender for](campaigns.md) Office 365のキャンペーン ビューの一Office 365利用可能 ( プラン 2)
- セキュリティ[運用チームが](threat-explorer.md)電子メールの調査中に複数のフィールドを検索およびフィルター処理できる脅威エクスプローラーの機能強化[:](investigate-malicious-email-that-was-delivered.md)(Microsoft Defender for Office 365 プラン 2)
  - 配信場所と特別なアクション
  - 方向性 (受信、送信、または組織内)
  - 高度な NOT フィルター (これらは、含まれているか、含めない、などを含む高度なフィルター オプションです)
  - 詳細な時間フィルター (日、時間、30 分)

- インシデント **ウィジェットが** アクション センター **ウィジェットに変更** されました。 (セキュリティ ウィジェットをコンプライアンス センターのセキュリティ &表示するには、[脅威の管理]**に移動します。** \>**レビュー**.)(Microsoft Defender for Office 365プラン 2)

- [セーフドキュメントのMicrosoft 365](safe-docs.md) **(プレビュー)**

## <a name="december-2019"></a>2019 年 12 月

- [オフライン分析用の URL クリック データ](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections)のエクスポート (Microsoft Defender for Office 365プラン 1 またはプラン 2)

- [Microsoft Defender のキャンペーン ビューを使用して、Office 365 (**プレビュー**)](campaigns.md) (Microsoft Defender for Office 365 プラン 2)

## <a name="november-2019"></a>2019 年 11 月

- [侵害された新しいユーザー検出](address-compromised-users-quickly.md)および応答機能 (**プレビュー**) (Microsoft Defender for Office 365プラン 2)

## <a name="september-2019"></a>2019 年 9 月

- [自動調査と対応機能を採用](automated-investigation-response-office.md)する (Microsoft Defender for Office 365プラン 2)

- [Microsoft Defender と統合して、Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)管理アクティビティ API (Defender for Office 365 プラン 2) を使用して、Office 365調査および応答イベントを自動化します。

- [電子メール ヘッダーを表示し、電子メール本文](investigate-malicious-email-that-was-delivered.md)をダウンロードする (Microsoft Defender for Office 365プラン 1 またはプラン 2)

## <a name="august-2019"></a>2019 年 8 月

- [メールのタイムラインを表示](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email)する (Microsoft Defender for Office 365プラン 1 またはプラン 2)

## <a name="july-2019"></a>2019 年 7 月

- [メール メッセージの配信アクションと場所を](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location)確認する (Microsoft Defender for Office 365プラン 1 または 2)

## <a name="june-2019"></a>2019 年 6 月

- [フィッシング URL を表示し、[評](threat-explorer.md#view-phishing-url-and-click-verdict-data)決データ] をクリックします (Microsoft Defender for Office 365プラン 1 またはプラン 2)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender for Office 365 プラン 1 およびプラン 2

Microsoft Defender for Office 365プランが 2 つ用意されていますか? [各プランに含まれる内容の詳細については、以下を参照してください](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。

## <a name="see-also"></a>関連項目

[Microsoft 365ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)

[Microsoft Defender for Office 365 サービスの説明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
