---
title: Microsoft 365 Lighthouseの [ユーザー] ページの概要
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: ragovind
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、[ユーザー] ページについて説明します。
ms.openlocfilehash: 05c889167cc7359900c0dea3396e657c0aa93fba
ms.sourcegitcommit: c314e989202dc1c9c260fffd459d53bc1f08514e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2022
ms.locfileid: "66717562"
---
# <a name="overview-of-the-users-page-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseの [ユーザー] ページの概要 

Microsoft 365 Lighthouseでは、左側のナビゲーション ウィンドウの [ユーザー] の下にあるリンクのいずれかを選択して、顧客テナント アカウント間で **ユーザー** を管理できます。 [ユーザー] ページでは、ユーザーを検索し、ユーザー アカウントのセキュリティ状態を評価して操作できます。 リスクの高いユーザーと、多要素認証とセルフサービスパスワードリセットの状態に関する分析情報を表示することもできます。  
  
## <a name="search-users-tab"></a>[ユーザーの検索] タブ  
  
[ユーザーの検索] タブから、テナント間で特定のユーザーをすばやく検索し、ユーザー アカウント情報の更新、パスワードのリセット、ライセンスの割り当て、ユーザーのグループ、メールボックス、OneDrive の管理などの一般的なユーザー管理タスクを実行できます。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-search-users-tab.png" alt-text="[ユーザーの検索] タブのスクリーンショット。":::

## <a name="risky-users-tab"></a>[危険なユーザー] タブ

[危険なユーザー] タブには、危険な動作のフラグが設定されているテナント全体のユーザー アカウントが表示されます。 検出されたリスクの詳細を表示したり、ユーザーのパスワードをリセットしたりサインインをブロックしたりしてリスクを軽減したりするには、任意のユーザーを選択します。 リスクの種類と検出の詳細については、「 [リスクとは」](/azure/active-directory/identity-protection/concept-identity-protection-risks)を参照してください。

[危険なユーザー] タブには、次のオプションも含まれています。
- **エクスポート：** デバイス コンプライアンス データを Excel のコンマ区切り値 (.csv) ファイルにエクスポートする場合に選択します。
- **更新：** 最新のデバイス コンプライアンス データを取得する場合に選択します。
- **侵害されたユーザーを確認します。** ユーザーが侵害されたことを確認する場合に選択します。
- **ユーザーのリスクを無視する:** ユーザー リスクを無視する場合に選択します。  
- **パスワードのリセット:** ユーザー パスワードを変更またはリセットする場合に選択します。
- **サインインをブロックする:** すべてのユーザーがこのユーザーとしてサインインできないようにする場合に選択します。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-risky-users-tab.png" alt-text="[危険なユーザー] タブのスクリーンショット。":::

## <a name="multifactor-authentication-tab"></a>[多要素認証] タブ

[多要素認証] タブには、テナント全体での多要素認証 (MFA) 有効化の状態に関する詳細な情報が表示されます。 一覧から任意のテナントを選択すると、MFA を必要とする条件付きアクセス ポリシーが既に構成されていることや、MFA にまだ登録していないユーザーなど、そのテナントの詳細が表示されます。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-mfa-tab.png" alt-text="[多要素認証] タブのスクリーンショット。":::

## <a name="password-reset-tab"></a>[パスワード リセット] タブ

[パスワード リセット] タブには、テナント間でのセルフサービス パスワード リセット有効化の状態に関する詳細情報が表示されます。 また、有効になっているが、自分でパスワードをリセットする前に登録する必要があるユーザーに関する分析情報も提供されます。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-password-reset-tab.png" alt-text="[パスワードリセット] タブのスクリーンショット。":::

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouseデバイス コンプライアンス ページの概要](m365-lighthouse-device-compliance-page-overview.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
