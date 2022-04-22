---
title: Microsoft 365 Lighthouseでテナント リストを管理する
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
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) の場合は、テナント リストを管理する方法について説明します。
ms.openlocfilehash: b4bffcfd5b8962253e68938a956949ca8470f818
ms.sourcegitcommit: 339d2c2ffea06726f69429f73c1113c649f37b18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2022
ms.locfileid: "65022429"
---
# <a name="manage-your-tenant-list-in-microsoft-365-lighthouse"></a>Microsoft 365 Lighthouseでテナント リストを管理する

Microsoft 365 Lighthouseでテナント リストを管理するために、カスタム タグをテナントに適用できます。 これらのタグは、テナントを整理するために使用でき、関連するテナント セットで使用可能な既存のビューと分析情報をフィルター処理するのにも役立ちます。 タグは、[テナント] ページから管理できます。 作成して割り当てると、タグに基づいてテナント、ユーザー、デバイス、脅威管理、およびWindows 365 ページ内のデータをフィルター処理できます。

## <a name="before-you-begin"></a>はじめに

テナント タグを管理するには、次の手順を実行する必要があります。

- [Microsoft 365 Lighthouseの要件を](m365-lighthouse-requirements.md)満たします。

- Microsoft 365 Lighthouse[のサインアップに関する](m365-lighthouse-sign-up.md)記事で説明されているプロセスを完了します。

- ポータルセキュリティの構成に関する記事で説明されているプロセス[Microsoft 365 Lighthouse](m365-lighthouse-configure-portal-security.md)完了します。

- パートナー テナントのグローバル管理者になります。

## <a name="create-a-tag"></a>タグを作成する

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **テナント**] を選択します。

2. [ **タグの管理**] を選択します。

3. [ **タグの管理** ] ウィンドウで、[ **タグの追加**] を選択します。

4. 名前と説明を入力します。

5. **[保存]** を選択します。

## <a name="edit-a-tag"></a>タグを編集する

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **テナント**] を選択します。

2. [ **タグの管理**] を選択します。

3. [ **タグの管理** ] ウィンドウで、編集するタグを選択します。

4. 必要に応じて、名前や説明を編集します。

5. **[保存]** を選択します。

## <a name="assign-a-tag"></a>タグを割り当てる

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **テナント**] を選択します。

2. テナントの一覧から、タグ付けするテナントの横にある 3 つのドット (その他のアクション) を選択します。

3. **[タグ**] を選択します。

4. 一覧からタグを選択します。 一度に選択できるタグは 1 つだけです。

テナントに既に割り当てられているタグには、タグ名の右側にチェック マークが付けられます。 また、一覧の各テナントの横にあるチェック ボックスをオンにし、[タグの **割り当て**] を選択してから、一覧からタグを選択して、タグを複数のテナントに割り当てることもできます。

> [!NOTE]
> 最大 30 個の一意のタグを作成し、必要な数のテナントに割り当てることができます。

## <a name="delete-a-tag"></a>タグを削除する

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **テナント**] を選択します。

2. [ **タグの管理**] を選択します。

3. [ **タグの管理** ] ウィンドウで、削除するタグを選択します。

4. [ **タグの削除] を選択します**。

## <a name="remove-a-tag"></a>タグを削除する

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **テナント**] を選択します。

2. テナントの一覧から、編集するテナントの横にある 3 つのドット (その他のアクション) を選択します。

3. **[タグ**] を選択します。

4. 削除するタグを選択します。

現在割り当てられているタグには、名前の右側にチェック マークが付けられます。 複数のテナントからタグを削除するには、一覧の各テナントの横にあるチェック ボックスをオンにし、[ **タグの割り当て**] を選択してから、一覧からチェック されたタグを選択します。

## <a name="next-steps"></a>次の手順

タグを作成して割り当てた後、それらを使用してテナントをフィルター処理できます。 他のページ (ユーザー、デバイス、脅威管理、またはWindows 365) に移動し、テナント フィルターから 1 つ以上のタグを選択します。 各ページに基づいて特定のビューをサポートする新しいタグを作成できます。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouseにサインアップする](m365-lighthouse-sign-up.md) (記事) [Microsoft 365 Lighthouseの [デバイス コンプライアンス] ページの概要](m365-lighthouse-device-compliance-page-overview.md) (記事) [Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)
