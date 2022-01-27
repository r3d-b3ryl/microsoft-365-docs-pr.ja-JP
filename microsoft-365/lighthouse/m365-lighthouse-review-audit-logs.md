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
ms.openlocfilehash: b07f308e5098ab5b7c9b091d3fe55b882cbb8649
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2022
ms.locfileid: "62242202"
---
# <a name="review-audit-logs"></a>監査ログの確認

> [!NOTE]
> この記事で説明する機能はプレビュー段階であり、変更される可能性があり、[要件](m365-lighthouse-requirements.md)を満たすパートナーのみが利用できます。 組織に Microsoft 365 Lighthouse がない場合は、「[Microsoft 365 Lighthouse にサインアップする](m365-lighthouse-sign-up.md)」を参照してください。
Microsoft 365 Lighthouse監査ログには、ライトハウスまたは他のサービスの変更を生成するMicrosoft 365記録されます。 作成、編集、削除、割り当て、リモート 操作はすべて、確認できる監査イベントを作成します。 既定では、すべてのお客様に対して監査が有効です。 それを無効にすることはできません。

## <a name="before-you-begin"></a>はじめに

監査ログを表示するには、次のいずれかのアクセス許可が必要です。

- Azure ADロール - パートナー テナントのグローバル管理者

- パートナー センターの役割 - 管理者エージェント

## <a name="review-logs"></a>ログの確認

1. ライトハウスの左側のナビゲーション ウィンドウで、[監査ログ] **を選択します**。

    > [!NOTE]
    > 新しいログを表示するには、最大で 1 時間かかる場合があります。 それぞれのサービスに移動して、最新の変更点を確認します。

2. ログをフィルター処理するには、次のオプションを使用してリストを絞り込む必要があります。

    - **日付範囲** - 前の月、週、または日。
    - **テナント -** テナント タグまたは顧客テナント名。
    - **Area** - アクションが開始された領域。 この領域は、左側のナビゲーション バーのエントリに対応します。
    - **Activity** - Microsoft 365に対応するアクティビティの種類を指定します。 詳細については、「Activity Types table」を参照してください。
    - **によって開始される**- Whoを開始しました。

3. リストからログを選択すると、要求本文を含む詳細が **表示** されます。

[ **エクスポート]** を選択して、ログ データをコンマ区切り値 (.csv) ファイルにエクスポートします。

## <a name="activity-types"></a>アクティビティの種類

次の表は、ライトハウス監査ログ内でキャプチャされるアクティビティの種類の一覧です。 新しいアクションが作成されると、リストは変更される可能性があります。 監査ログのアクティビティ値を使用して、開始されたアクションを確認できます。

| アクティビティ名    | Microsoft 365 Lighthouse | 開始されたアクション  | サービスが影響を受け           |
|------------------|----------------------------------|-------------------|----------------------------|
|**offboardTenant**        | テナント          | 顧客の非アクティブ化  | Microsoft 365 Lighthouse   |
|**resetTenantOnboardingStatus**              | テナント                          | 顧客の対応                                              | Microsoft 365 Lighthouse   |
| **tenantTags**                               | テナント                          | タグを作成または削除する                                           | Microsoft 365 Lighthouse   |
|**assignTag**                                | テナント                          | 顧客からのタグの適用                                      | Microsoft 365 Lighthouse   |
|**unassignTag**                              | テナント                          | 顧客からタグを削除する                                    | Microsoft 365 Lighthouse   |
|**tenantCustomizedInformation**              | テナント                          | 顧客の Web サイトまたは連絡先情報を作成、更新、または削除する | Microsoft 365 Lighthouse   |
|**changeDeploymentStatus**                   | テナント                          | 展開計画のアクション 計画の状態                        | Microsoft 365 Lighthouse   |
| **conditionalAccessPolicy**                  | テナント                          | 管理者に MFA を要求する                                           | Azure AD                   |
| **conditionalAccessPolicy**                  | テナント                          | ユーザーに MFA を要求する                                           | Azure AD                   |
| **conditionalAccessPolicy**                  | テナント                          | 従来の認証をブロックする                                      | Azure AD                   |
| **deviceRegistrationPolicy**                 | テナント                          | デバイスの登録を設定する                                         | Azure AD                   |
|**deviceConfiguration**                      | テナント                          | Microsoft Defender の構成                                     | Microsoft エンドポイント マネージャー |
| **deviceCompliancePolicy**                   | テナント                          | デバイス コンプライアンス ポリシーの構成                             | Microsoft エンドポイント マネージャー |
| **confirmUsersCompromised**                  | ユーザー                            | ユーザーが侵害されたのを確認する                                        | Azure AD                   |
| **dismissUsersRisk**                         | ユーザー                            | ユーザー リスクの却下                                                | Azure AD                   |
| **resetUserPassword**                        | ユーザー                            | パスワードのリセット                                                   | Azure AD                   |
| **blockUserSignin**                          | ユーザー                            | サインインをブロックする                                                     | Azure AD                   |
| **setCustomerSecurityDefaultsEnabledStatus** | ユーザー                            | セキュリティの既定値を使用して MFA を有効にする                               | Azure AD                   |
| **syncDevice**                               | デバイス                          | 同期                                                             | Microsoft エンドポイント マネージャー |
|**restartDevice**                            | デバイス                          | Restart                                                          | Microsoft エンドポイント マネージャー |
| **windowsDefenderScan**                      | 脅威の管理                | フル スキャン                                                       | Microsoft エンドポイント マネージャー |
| **windowsDefenderScan**                      | 脅威の管理                | クイック スキャン                                                       | Microsoft エンドポイント マネージャー |
| **rebootNow**                                | 脅威の管理                | 再起動                                                           | Microsoft エンドポイント マネージャー |
| **windowsDefenderUpdateSignatures**          | 脅威の管理                | ウイルス対策の更新                                                | Microsoft エンドポイント マネージャー |
| **reprovision**                              | テナント                          | Retry Provisioning                                               | Windows 365                |

## <a name="next-steps"></a>次の手順

詳細が必要な場合は、Microsoft Graph API を使用して、より多くの監査イベントにアクセスできます。 詳細については、「Overview [for multi-tenant management using the Microsoft 365 Lighthouse API」を参照してください](/graph/managedtenants-concept-overview)。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
