---
title: Microsoft Defender for Office 365 の新機能
description: Microsoft Defender for microsoft Defender for Office 365 で利用できる新機能について説明します。
keywords: 365 atp、ga、Office一般提供、機能、利用可能、新機能の新機能
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
ms.date: 01/12/2021
ms.custom: seo-marvel-apr2020
ms.reviewer: vippand
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c79a235051897f19ca2c3f42b220c87a48cfac3f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064436"
---
# <a name="whats-new-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

この記事では、Microsoft Defender for microsoft Defender for Office一覧を示します。 現在プレビュー中の機能は (プレビュー) **で示されます**。

> [!TIP]
> Microsoft Defender for Office 365 がありませんか? [試用版を開始するために販売に問い合わせ。](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)

## <a name="februarymarch-2021"></a>2021 年 2 月/3 月 

- 検索エクスペリエンスでのアラート ID の統合 (アラート ID とAlert-Explorerナビゲーションを使用[した検索](threat-explorer.md))
- 狩猟エクスペリエンスでのレコードのエクスポートの制限を 9990 から 200,000 に [増やす](threat-explorer.md)
- 試用版テナントのエクスプローラー (およびリアルタイム検出) データの保持と検索の制限を 7 (前の制限) から 30 日間のハンティング エクスペリエンス [に拡張する](threat-explorer.md)
- 保護されたユーザーまたはドメインに対する偽装攻撃を検索するための、エクスプローラー内の偽装ドメインと偽装ユーザー (およびリアルタイムの検出) と呼ばれる新しい検索ピボット。 詳細については、「詳細」を [参照してください](threat-explorer.md#view-phishing-emails-sent-to-impersonated-users-and-domains)。 (Microsoft Defender for Office 365 プラン 1 またはプラン 2)

## <a name="december-2020"></a>2020年12月

- [365 で既定でセキュリティOffice](secure-by-default.md)
- 自動調査の機能強化: 手動でトリガーされた電子メール調査に関する一般的なアラート、メールボックスの変更を別のエンティティ カテゴリとして扱い、冗長な URL ブロック アクションを削除し、ユーザーが侵害された調査のために送信メール クラスターを作成します。

## <a name="november-2020"></a>2020 年 11 月

- Review > アクション センター > メール送信とアクション ログからの修復のエクスポート制限を更新しました (Defender for Office 365 Plan 2)

## <a name="septemberoctober-2020"></a>2020 年 9 月/10 月

- [Configuration Analyzer を使用してポリシーを確認する](configuration-analyzer-for-security-policies.md)
- トップ ターゲットユーザー、トランスポート ルール、コネクタを含む脅威エクスプローラーの拡張機能[(Threat](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) [Explorer](threat-explorer.md)の Office 365 の Defender 情報 (テナント/ユーザー ポリシーによって電子メールが許可/ブロックされました) (Defender for Office 365 Plan 2)
- 脅威エクスプローラー (マルウェア、フィッシング、スパム、またはなし) で URL の脅威を検出する [(Defender](threat-explorer.md#threats-in-urls) for Office 365 プラン 2)
- [脅威、追加](threat-explorer.md#improvements-to-the-threat-hunting-experience-upcoming) アクション、配信場所、および更新されたタイムライン ビューに関する更新プログラムを含むハンティング エクスペリエンス脅威エクスプローラーの機能強化 (Defender for Office 365 プラン 2)

## <a name="julyaugust-2020"></a>2020 年 7 月/8 月

- [ハンティング エクスペリエンスの改善点](threat-explorer.md#improvements-to-threat-hunting-experience) (Microsoft Defender for Office 365 プラン 1 またはプラン 2)
- [事前設定されたセキュリティ ポリシーを使用して推奨設定を簡単に適用する](preset-security-policies.md)

## <a name="marchapril-2020"></a>2020 年 3 月/4 月

- 調査と対応 [を自動化](address-compromised-users-quickly.md) して、侵害されたユーザー アカウントに対処する機能が一般に利用可能になります。 (Microsoft Defender for Office 365 プラン 2)

## <a name="januaryfebruary-2020"></a>2020 年 1 月/2 月

- Microsoft Defender for [microsoft Defender for Office 365](campaigns.md)のキャンペーン ビューの一般提供 (Microsoft Defender for Office 365 プラン 2)
- 脅威[エクスプローラーの機能強化](threat-explorer.md): (Microsoft Defender for Office 365 Plan 2) [](investigate-malicious-email-that-was-delivered.md)
  - 配信場所と特別なアクション
  - 方向性 (受信、送信、または組織内)
  - 高度な NOT フィルター (これらは、含まれているか、含めない、などを含む高度なフィルター オプションです)
  - 詳細な時間フィルター (日、時間、30 分)

- インシデント **ウィジェットが** アクション センター **ウィジェットに変更** されました。 (セキュリティ ウィジェットを表示するには、セキュリティ &コンプライアンス センターで、[脅威の管理]**に移動します。** \>**レビュー**.)(Microsoft Defender for Office 365 プラン 2)

- [Microsoft 365 の安全な](safe-docs.md)ドキュメント **(プレビュー)**

## <a name="december-2019"></a>2019 年 12 月

- [オフライン分析用の](threat-explorer.md#new-features-in-threat-explorer-and-real-time-detections) URL クリック データのエクスポート (Microsoft Defender for Office 365 プラン 1 またはプラン 2)

- [Microsoft Defender でキャンペーン ビューを使用して Office 365 (**プレビュー**) (Microsoft](campaigns.md) Defender for Office 365 Plan 2)

## <a name="november-2019"></a>2019 年 11 月

- [侵害された新しいユーザー検出](address-compromised-users-quickly.md) および応答機能 **(プレビュー**) (Microsoft Defender for Office 365 プラン 2)

## <a name="september-2019"></a>2019 年 9 月

- [自動調査と対応機能を採用](automated-investigation-response-office.md) する (Microsoft Defender for Office 365 プラン 2)

- [Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 管理アクティビティ API (defender for Office 365 プラン 2) を使用して、microsoft Defender と統合して、Office 365 の自動調査および応答イベントを実行します。

- [電子メール ヘッダーを表示し、電子](investigate-malicious-email-that-was-delivered.md) メール本文をダウンロードする (Microsoft Defender for Office 365 プラン 1 またはプラン 2)

## <a name="august-2019"></a>2019 年 8 月

- [メールのタイムラインを表示](investigate-malicious-email-that-was-delivered.md#view-the-timeline-of-your-email) する (Microsoft Defender for Office 365 プラン 1 またはプラン 2)

## <a name="july-2019"></a>2019 年 7 月

- [メール メッセージの配信アクションと場所を](investigate-malicious-email-that-was-delivered.md#check-the-delivery-action-and-location) 確認する (Microsoft Defender for Office 365 プラン 1 または 2)

## <a name="june-2019"></a>2019 年 6 月

- [フィッシング URL を表示し、[](threat-explorer.md#view-phishing-url-and-click-verdict-data) 評決データ] をクリックします (Microsoft Defender for Office 365 プラン 1 またはプラン 2)

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender for Office 365 プラン 1 およびプラン 2

Microsoft Defender for Office 365 は 2 つのプランで利用できます。 [各プランに含まれる内容の詳細については、以下を参照してください](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2)。

## <a name="see-also"></a>関連項目

[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)

[Microsoft Defender for Office 365 サービスの説明](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)