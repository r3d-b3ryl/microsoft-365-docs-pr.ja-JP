---
title: Microsoft 365 Lighthouseの [ユーザー] ページの概要
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、[ユーザー] ページについて説明します。
ms.openlocfilehash: c4ae82485c2f9b57b1e47fe61624e0ccac34d067
ms.sourcegitcommit: 339d2c2ffea06726f69429f73c1113c649f37b18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65022495"
---
# <a name="overview-of-the-users-page-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseの [ユーザー] ページの概要 

Microsoft 365 Lighthouseでは、左側のナビゲーション ウィンドウで [**ユーザー**] を選択して [ユーザー] ページを開くことで、顧客テナント アカウント全体のユーザーを管理できます。 このページでは、ユーザーを検索し、ユーザー アカウントのセキュリティ状態を評価して操作できます。 リスクの高いユーザーと、多要素認証とセルフサービスパスワードリセットの状態に関する分析情報を表示することもできます。  
  
## <a name="search-users-tab"></a>[ユーザーの検索] タブ  
  
[ユーザーの検索] タブから、テナント間で特定のユーザーをすばやく検索し、アカウント パスワードのリセットなどの基本的なユーザー管理アクションを実行できます。

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-search-users-tab.png" alt-text="[ユーザーの検索] タブのスクリーンショット。":::

## <a name="risky-users-tab"></a>[危険なユーザー] タブ

[危険なユーザー] タブには、危険な動作のフラグが設定されているテナント全体のユーザー アカウントが表示されます。 検出されたリスクの詳細を表示したり、ユーザーのパスワードをリセットしたりサインインをブロックしたりしてリスクを軽減したりするには、任意のユーザーを選択します。 リスクの種類と検出の詳細については、「 [リスクとは」](/azure/active-directory/identity-protection/concept-identity-protection-risks)を参照してください。

[危険なユーザー] タブには、次のオプションも含まれています。
- **エクスポート：** デバイス コンプライアンス データをExcelコンマ区切り値 (.csv) ファイルにエクスポートする場合に選択します。
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
