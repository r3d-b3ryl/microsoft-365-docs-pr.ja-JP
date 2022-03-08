---
title: Microsoft 365 Lighthouse ユーザー ページの概要
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
description: 管理サービス プロバイダー (MSP) が Microsoft 365 Lighthouseユーザー ページについて説明します。
ms.openlocfilehash: fad5ff4b41b43efb68c7e230401b80e50cea95a4
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329941"
---
# <a name="microsoft-365-lighthouse-users-page-overview"></a>Microsoft 365 Lighthouse ユーザー ページの概要 

Microsoft 365 Lighthouse左側のナビゲーション ウィンドウで [ユーザー] を選択して [ユーザー] ページを開き、顧客テナント アカウント間でユーザーを管理できます。 このページから、ユーザーを検索し、ユーザー アカウントのセキュリティ状態を評価して実行できます。 リスクの高いユーザーと、多要素認証とセルフサービス パスワードのリセットの状態に関する分析情報を表示できます。  
  
## <a name="search-users-tab"></a>[ユーザーの検索] タブ  
  
[ユーザーの検索] タブでは、テナント間で特定のユーザーをすばやく検索し、アカウント パスワードのリセットなどの基本的なユーザー管理アクションを実行できます。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-search-users-tab.png" alt-text="[ユーザーの検索] タブのスクリーンショット。":::

## <a name="risky-users-tab"></a>[危険なユーザー] タブ

[危険なユーザー] タブには、リスクの高い動作のフラグが設定されているテナント全体のユーザー アカウントが表示されます。 検出されたリスクに関する詳細を表示したり、ユーザーのパスワードをリセットしたり、サインインをブロックしたりしてリスクを軽減するには、任意のユーザーを選択します。 リスクの種類と検出の詳細については、「リスク [とは」を参照してください](/azure/active-directory/identity-protection/concept-identity-protection-risks)。

[危険なユーザー] タブには、次のオプションも含まれています。
- **エクスポート:** デバイス コンプライアンス データをコンマ区切り (Excel) ファイルにエクスポート.csvします。
- **更新:** 最新のデバイス コンプライアンス データを取得する場合に選択します。
- **ユーザーが侵害されたのを確認します。** ユーザーが侵害されたと確認する場合に選択します。
- **ユーザーのリスクを却下する:** ユーザー リスクを却下する場合に選択します。  
- **パスワードのリセット:** ユーザー パスワードを変更またはリセットする場合に選択します。
- **サインインをブロックする:** このユーザーとしてサインインするユーザーを防止する場合に選択します。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-risky-users-tab.png" alt-text="[危険なユーザー] タブのスクリーンショット。":::

## <a name="multifactor-authentication-tab"></a>[多要素認証] タブ

[多要素認証] タブには、テナント全体の多要素認証 (MFA) 有効化の状態に関する詳細情報が表示されます。 一覧で任意のテナントを選択すると、MFA を必要とする条件付きアクセス ポリシーが既に構成されている場合や、MFA にまだ登録していないユーザーなど、そのテナントの詳細が表示されます。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-mfa-tab.png" alt-text="[多要素認証] タブのスクリーンショット。":::

## <a name="password-reset-tab"></a>[パスワードのリセット] タブ

[パスワードのリセット] タブには、テナント全体のセルフサービス パスワードリセット有効化の状態に関する詳細情報が表示されます。 また、自分でパスワードをリセットする前に、有効になっているが登録が必要なユーザーに関する分析情報も提供します。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-password-reset-tab.png" alt-text="[パスワードのリセット] タブのスクリーンショット。":::

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouseコンプライアンス ページの概要](m365-lighthouse-device-compliance-page-overview.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
