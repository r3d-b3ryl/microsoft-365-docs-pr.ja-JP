---
title: Microsoft 365 Lighthouseで監査ログを確認する
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: vivkuma
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、監査ログを確認する方法について説明します。
ms.openlocfilehash: c24e321cae13e6e604f7daba79f820d0b1bc6bb3
ms.sourcegitcommit: eb81b49205cbc66b021326b8e2c00a8336b4a2fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2022
ms.locfileid: "67315616"
---
# <a name="review-audit-logs-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseで監査ログを確認する

Microsoft 365 Lighthouse監査ログには、Lighthouse またはその他の Microsoft 365 サービスで変更を生成するアクションが記録されます。 作成、編集、削除、割り当て、リモート 操作はすべて、確認できる監査イベントを作成します。 既定では、すべてのお客様に対して監査が有効です。 それを無効にすることはできません。

## <a name="before-you-begin"></a>はじめに

監査ログを表示するには、次のいずれかのアクセス許可が必要です。

- Azure Active Directory (Azure AD) ロール - パートナー テナントのグローバル管理者

- Microsoft パートナー センター ロール - 管理 エージェント

## <a name="review-audit-logs"></a>監査ログを確認する

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **監査ログ**] を選択します。

    > [!NOTE]
    > 新しいログを表示するには、最大で 1 時間かかる場合があります。 それぞれのサービスに移動して、最新の変更を確認します。

2. 必要に応じて、次のオプションを使用してログをフィルター処理します。

    - **日付範囲** - 前の月、週、または日。
    - **テナント** - テナント タグまたは顧客テナント名。
    - **アクティビティ** - 実行されたアクションに対応する Microsoft 365 アクティビティの種類。 詳細については、「 [アクティビティ](#activities) 」の表を参照してください。
    - **[開始者** ] - アクションを開始したユーザー。

3. 一覧からログを選択すると、 **要求** 本文を含む完全な詳細が表示されます。

    ログ データをコンマ区切り値 (.csv) ファイルにエクスポートするには、[ **エクスポート**] を選択します。

## <a name="activities"></a>アクティビティ

次の表に、Lighthouse 監査ログ内でキャプチャされたアクティビティの一覧を示します。 新しいアクションが作成されると、リストは変更される可能性があります。 監査ログに一覧表示されているアクティビティを使用して、開始されたアクションを確認できます。<br><br>

| アクティビティ名 | ライトハウスのエリア | 開始されたアクション | 影響を受けたサービス |
|--|--|--|--|
| **適用** または **デプロイする** | テナント | 展開計画を適用する | Azure AD、Microsoft エンドポイント マネージャー (MEM) |
| **assignTag** | テナント | 顧客からタグを適用する | 灯台 |
| **changeDeploymentStatus** または **assign** | テナント | 展開計画のアクション プランの状態を更新する | 灯台 |
| **offboardTenant** | テナント | 顧客を非アクティブ化する | 灯台 |
| **resetTenantOnboardingStatus** | テナント | 顧客の事後対応 | 灯台 |
| **tenantTags** | テナント | タグを作成または削除する | 灯台 |
| **tenantCustomizedInformation** | テナント | 顧客の Web サイトまたは連絡先情報を作成、更新、または削除する | 灯台 |
| **unassignTag** | テナント | 顧客からタグを削除する | 灯台 |
| **検証** | テナント | デプロイ計画をテストする | Azure AD |
| **blockUserSignin** | ユーザー | サインインをブロックする | Azure AD |
| **confirmUsersCompromification** | ユーザー | ユーザーが侵害されていることを確認する | Azure AD |
| **dismissUsersRisk** | ユーザー | ユーザー リスクを無視する | Azure AD |
| **resetUserPassword** | ユーザー | パスワードのリセット | Azure AD |
| **setCustomerSecurityDefaultsEnabledStatus** | ユーザー | セキュリティの既定値を使用して多要素認証 (MFA) を有効にする | Azure AD |
| **restartDevice** | デバイス | Restart | Mem |
| **syncDevice** | デバイス | 同期 | Mem |
| **rebootNow** | 脅威の管理 | 再起動 | Mem |
| **reprovision** | Windows 365 | 再試行プロビジョニング | Windows 365 |
| **windowsDefenderScanFull** | 脅威の管理 | フル スキャン | Mem |
| **windowsDefenderScan** | 脅威の管理 | クイック スキャン | Mem |
| **windowsDefenderUpdateSignatures** | 脅威の管理 | ウイルス対策を更新する | Mem |

## <a name="next-steps"></a>次の手順

必要に応じて、Microsoft Graph APIを使用して、より多くの監査イベントにアクセスします。 詳細については、「[Microsoft 365 Lighthouse API を使用したマルチテナント管理の概要](/graph/managedtenants-concept-overview)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)\
[Microsoft 365 Lighthouseで Azure Active Directory ロールを表示](m365-lighthouse-view-your-roles.md)する (記事)