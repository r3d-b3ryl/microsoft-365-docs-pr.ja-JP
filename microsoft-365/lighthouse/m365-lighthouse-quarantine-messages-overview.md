---
title: Microsoft 365 Lighthouseの検疫済みメッセージの概要
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: shcallaw
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、検疫されたメッセージを管理する方法について説明します。
ms.openlocfilehash: 3a295802ba806c48f01f6f64c8b148169fe28102
ms.sourcegitcommit: 85799f0efc06037c1ff309fe8e609bbd491f9b68
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66574365"
---
# <a name="overview-of-quarantined-messages-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseの検疫済みメッセージの概要

Microsoft 365 Lighthouseでは、すべての顧客テナントで検疫された電子メールに関する分析情報と情報を確認できます。 1 つのビューから、検疫されたメールをトリアージし、適切なアクションを実行できます。 このデータは、テナントが Exchange Online Protection (EOP) と Microsoft Defender for Office365 プラン 1 (MDO) を実装している場合に使用できます。

左側のナビゲーションまたは **ホーム** ページから **[データ保護**] を選択すると、情報にアクセスできます。

## <a name="quarantined-messages-page"></a>[検疫済みメッセージ] ページ

このページでは、顧客テナント全体の統合統計、検疫データの種類と量の傾向データ、個々の顧客テナントの検疫キューに関連する情報を表示できます。

[ **メッセージの状態]** セクションには、Lighthouse に現在オンボードされている対象テナント全体の統合ビューが表示されます。 ビューには次のものが含まれます。

- 検疫内のメッセージの合計
- レビューを待機しているメッセージの合計
- 現在、既定の検疫制限である 30 日間に近づいているメッセージが自動的に削除 (期限切れ) される予定です。
- 検疫から解放されたメッセージ
- すべてのテナントで影響を受けたメールボックスの合計数

データには過去 30 日間が反映されます。ただし、 **時間範囲** フィルターを使用してビューを変更できます。

**検疫****理由** グラフには、Exchange Online Protection (EOP) ポリシーと Microsoft Defender for Office365 プラン 1 (MDO) ポリシーの種類別の検疫カウントの内訳が含まれています。 これらの型には、次のものが含まれます。

- マルウェア
- フィッシング詐欺
- 高信頼フィッシング
- スパム
- 一括メール

検疫リストは、テナント別の検疫情報の並べ替え可能なビューです。 このビュー内では、次の情報でフィルター処理できます。

- **検疫の理由:** Any、Malware、フィッシング、高信頼フィッシング、スパム、一括メール
- **ポリシーの種類:** Any、マルウェア対策、フィッシング詐欺対策、スパム対策、安全な添付ファイル、トランスポート ルール、不明
- **有効期限が切れる前:** Any, Today, within 2 days, within 7 days

また、テナント、メッセージの状態、有効期限に基づいて列を調整したり、データを並べ替えたりすることもできます。

:::image type="content" source="../media/m365-lighthouse-data-protection/quarantine-email-page.png" alt-text="Microsoft 365 Lighthouseの [検疫メッセージ] ページ" lightbox="../media/m365-lighthouse-data-protection/quarantine-email-page.png":::

Microsoft **365 Defender** **の [メッセージへのリンクのコピー**] オプションには、テナントの電子メール検疫キューにアクセスして管理できるMicrosoft 365 Defender ポータルへのリンクが用意されています。 何らかのアクションを実行するには、事前に認証を行う必要があります。

## <a name="related-content"></a>関連コンテンツ

[検疫された電子メール メッセージ](../security/office-365-security/quarantine-email-messages.md) (記事)\
[EOP とDefender for Office 365セキュリティ設定に関する Microsoft の推奨事項](../security/office-365-security/recommended-settings-for-eop-and-office365.md) (記事)\
[Exchange Online Protection (EOP) の概要](../security/office-365-security/exchange-online-protection-overview.md) (記事)
