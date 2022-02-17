---
title: 監査ログの確認
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouse監査ログを確認する方法について説明します。
ms.openlocfilehash: 69eb057c0b6a7daf835ec613b7d386e1a7fbfbaa
ms.sourcegitcommit: 6e43aeff217afe97876137b1ead8df26db6e9937
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "62859243"
---
# <a name="review-audit-logs"></a>監査ログの確認

> [!NOTE]
> この記事で説明する機能はプレビュー段階であり、変更される可能性があり、[要件](m365-lighthouse-requirements.md)を満たすパートナーのみが利用できます。 組織に Microsoft 365 Lighthouse がない場合は、「[Microsoft 365 Lighthouse にサインアップする](m365-lighthouse-sign-up.md)」を参照してください。

Microsoft 365 Lighthouse監査ログには、ライトハウスまたは他のサービスの変更を生成するMicrosoft 365記録されます。 作成、編集、削除、割り当て、リモート 操作はすべて、確認できる監査イベントを作成します。 既定では、すべてのお客様に対して監査が有効です。 それを無効にすることはできません。

## <a name="before-you-begin"></a>始める前に

監査ログを表示するには、次のいずれかのアクセス許可が必要です。

- Azure Active Directory (Azure AD) 役割 - パートナー テナントのグローバル管理者

- Microsoft パートナー センターの役割 - 管理者エージェント

## <a name="review-audit-logs"></a>監査ログの確認

1. ライトハウスの左側のナビゲーション ウィンドウで、[監査ログ] **を選択します**。

    > [!NOTE]
    > 新しいログを表示するには、最大で 1 時間かかる場合があります。 それぞれのサービスに移動して、最新の変更点を確認します。

2. 必要に応じて、次のオプションを使用してログをフィルター処理します。

    - **日付範囲** - 前の月、週、または日。
    - **テナント -** テナント タグまたは顧客テナント名。
    - **Activity** - Microsoft 365に対応するアクティビティの種類を指定します。 詳細については、「Activities」テーブル [を参照](#activities) してください。
    - **によって開始される** - Whoアクションを開始します。

3. リストからログを選択すると、要求本文を含む詳細が **表示** されます。

    ログ データをコンマ区切り値 (.csv) ファイルにエクスポートするには、[エクスポート] を選択 **します**。

## <a name="activities"></a>アクティビティ

次の表に、ライトハウス監査ログ内でキャプチャされたアクティビティの一覧を示します。 新しいアクションが作成されると、リストは変更される可能性があります。 監査ログに一覧表示されているアクティビティを使用して、開始されたアクションを確認できます。<br><br>

| アクティビティ名 | ライトハウスのエリア | 開始されたアクション | サービスが影響を受け |
|--|--|--|--|
| **適用する** | テナント | 展開計画の適用 | Azure AD, Microsoft エンドポイント マネージャー (MEM) |
| **assignTag** | テナント | 顧客からのタグの適用 | ライトハウス |
| **changeDeploymentStatus** | テナント | 展開計画のアクション 計画の状態 | ライトハウス |
| **offboardTenant** | テナント | 顧客の非アクティブ化 | ライトハウス |
| **resetTenantOnboardingStatus** | テナント | 顧客の対応 | ライトハウス |
| **tenantTags** | テナント | タグを作成または削除する | ライトハウス |
| **tenantCustomizedInformation** | テナント | 顧客の Web サイトまたは連絡先情報を作成、更新、または削除する | ライトハウス |
| **unassignTag** | テナント | 顧客からタグを削除する | ライトハウス |
| **blockUserSignin** | ユーザー | サインインをブロックする | Azure AD |
| **confirmUsersCompromised** | ユーザー | ユーザーが侵害されたと確認する | Azure AD |
| **dismissUsersRisk** | ユーザー | ユーザー リスクの却下 | Azure AD |
| **resetUserPassword** | ユーザー | パスワードのリセット | Azure AD |
| **setCustomerSecurityDefaultsEnabledStatus** | ユーザー | セキュリティの既定値を使用して多要素認証 (MFA) を有効にする | Azure AD |
| **restartDevice** | デバイス | Restart | MEM |
| **syncDevice** | デバイス | 同期 | MEM |
| **rebootNow** | 脅威の管理 | 再起動 | MEM |
| **reprovision** | Windows 365 | プロビジョニングの再試行 | Windows 365 |
| **windowsDefenderScanFull** | 脅威の管理 | フル スキャン | MEM |
| **windowsDefenderScan** | 脅威の管理 | クイック スキャン | MEM |
| **windowsDefenderUpdateSignatures** | 脅威の管理 | ウイルス対策の更新 | MEM |

## <a name="next-steps"></a>次の手順

詳細が必要な場合は、Microsoft Graph API を使用して、より多くの監査イベントにアクセスします。 詳細については、「Overview [for multi-tenant management using the Microsoft 365 Lighthouse API」を参照してください](/graph/managedtenants-concept-overview)。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
