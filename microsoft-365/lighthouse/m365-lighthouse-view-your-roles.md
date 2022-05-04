---
title: Microsoft 365 LighthouseでAzure Active Directory ロールを表示する
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
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouseを使用するマネージド サービス プロバイダー (MSP) 技術者の場合は、組織が管理するさまざまな顧客テナントでAzure Active Directory (Azure AD) ロールを表示する方法について説明します。
ms.openlocfilehash: b4d3e461d6af940181156a95aada86d59553b11b
ms.sourcegitcommit: 7e0094ddff54bcbe5d691dba58d4c4fb86f8b1a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2022
ms.locfileid: "65188903"
---
# <a name="view-your-azure-active-directory-roles-in-microsoft-365-lighthouse"></a>Microsoft 365 LighthouseでAzure Active Directory ロールを表示する

この記事では、組織が管理するさまざまな顧客テナント間でAzure Active Directory (Azure AD) ロールを表示する方法について説明します。 自分のロールによって、Lighthouse で実行できるアクションが決まります。

## <a name="before-you-begin"></a>はじめに

Microsoft 365 Lighthouse サービスにオンボードされているパートナー テナントにアクセスできる必要があります。

## <a name="view-your-roles"></a>ロールを表示する

1. Lighthouse の左側のナビゲーション ウィンドウで、[ **テナント**] を選択します。

2. テナントの一覧から任意のテナント名を選択して、テナントの **[概要] ページを** 開きます。

3. [ **ロール]** の横で、テナントに保持しているロールの数を示すリンクを選択します。 [ **ロール]** ページが開きます。

    顧客テナントで 1 つ以上のロールを保持している場合、そのテナントの **[有効]** 列に緑色のチェックマークと、保持しているロールの数が表示されます。 テナントにロールを保持していない場合は、赤い **X** が表示されます。
 
4. 隣に緑色のチェックマークが付いた顧客テナントの場合は、テナントを展開して、そのテナントで保持しているロールの一覧を表示します。 Azure AD ロールと付与するアクセス許可の詳細については、[組み込みロールAzure AD](/azure/active-directory/roles/permissions-reference)参照してください。

    [ **ロール]** ページには、テナントに適用されているカスタム タグも表示されます。 割り当てられたロールまたはタグを使用して、ページ上のデータをフィルター処理できます。

## <a name="next-steps"></a>次の手順

Lighthouse で実行する必要があるアクションを実行するアクセス許可がない場合は、実行しようとしているアクションに適切なロールを割り当てることができるパートナー テナントの管理者に連絡します。

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365 Lighthouseのアクセス許可の概要](m365-lighthouse-overview-of-permissions.md) (記事)\
[Microsoft 365 Lighthouseでテナント リストを管理する](m365-lighthouse-manage-tenant-list.md) (記事)