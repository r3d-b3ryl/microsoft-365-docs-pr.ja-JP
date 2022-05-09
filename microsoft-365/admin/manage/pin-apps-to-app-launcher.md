---
title: ユーザーのアプリ起動ツールにアプリをピン留めする
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
- Adm_TOC
ms.service: o365-administration
ms.custom: admindeeplinkMAC
ms.localizationpriority: medium
description: グローバル管理者は、ユーザーのアプリ起動ツールに最大 3 つのアプリをピン留めできます。
ms.openlocfilehash: 7ff85e379198312666f03c2d7d6c8bb42b9e08d0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171845"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>ユーザーのアプリ起動ツールにアプリをピン留めする

Azure Active Directory ポータルのコントロールを使用して、Office.com に最大 3 つのアプリをピン留めし、組織内のすべてのユーザーのアプリ起動ツールを使用できます。 アプリケーションのグループを整理することもできます。 後で追加するすべてのアプリは、いつでもユーザーによって固定解除できます。 ユーザーのアプリをピン留めするには、クラウド アプリケーション管理者、Azure Active Directoryのアプリケーション管理者、またはOffice 365のグローバル管理者である必要があります。 管理者ロールの詳細については、[Microsoft 365の組み込みロール](/azure/active-directory/roles/permissions-reference)と[管理者ロール](../add-users/about-admin-roles.md)Azure AD参照してください。 

アプリ起動ツールとOffice.com の詳細については、[アプリ起動ツール](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)と、[office.com とOffice 365アプリ起動ツールに関するブログ記事の更新プログラムを](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)参照してください。

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Azure Active Directory ポータルを使用してアプリをピン留めする

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の Microsoft 365 管理センターに移動します。
2. 左側のナビゲーションで [**すべて表示**] を選択し、[**管理センター**] で **[Azure Active Directory**] を選択します。
3. **Azure Active Directory** で、**Enterprise applicationsUser** >  **設定を選択します**。
4. **[Office 365 設定**] セクションで、[アプリケーションの **追加**] を選択します。
5. ユーザーのアプリ起動ツールにピン留めするアプリケーションを選択し、[ **追加**] を選択します。

:::image type="content" source="../../media/add-apps.png" alt-text="アプリをピン留めするための設定をMicrosoft 365します。":::

### <a name="pin-a-custom-app"></a>カスタム アプリをピン留めする

> [!NOTE]
> ユーザー インターフェイスは、この機能を使用するために追加のAzure AD ライセンスを購入する必要があるかどうかを示します。 詳細については、[Azure Active Directory価格に関するページを](https://azure.microsoft.com/pricing/details/active-directory/)参照してください。

1. **Azure Active Directory** で、[すべてのアプリケーション] ページの上部にある **[Enterprise** > アプリケーション **新しい****アプリケーション**] を選択します。
2. [**アプリケーションの追加]** ページで、プレビュー バージョンのAzure Active Directoryの場合は、[**ギャラリー以外のアプリケーション**] または [**独自のアプリケーションの作成**] を選択します。 
3. アプリケーションの名前を入力し、[ **ユーザーとグループ** ] タブにユーザーを割り当てます。
4. **[プロパティ**] タブを使用して、アプリのアイコンをアップロードします。
5. アプリに URL を割り当てるには、[ **シングル サインオン** ] タブで [ **リンク]** を選択し、URL を入力します。
6. **[保存]** を選択します。

## <a name="create-application-collections"></a>アプリケーション コレクションを作成する

また、組織内のユーザーのアプリケーション コレクションを作成することもできます。 手順については、[Azure portalのマイ アプリ ポータルでコレクションを作成する方法に関する記事を参照](/azure/active-directory/manage-apps/access-panel-collections)してください。