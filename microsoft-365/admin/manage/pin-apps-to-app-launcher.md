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
ms.openlocfilehash: a1f0fb9caab7c32936b5b0e99196decb965ab9f5
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67359211"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>ユーザーのアプリ起動ツールにアプリをピン留めする

Azure Active Directory ポータルのコントロールを使用して、最大 3 つのアプリを Office.com にピン留めし、組織内のすべてのユーザーのアプリ起動ツールをピン留めできます。 アプリケーションのグループを整理することもできます。 後で追加するすべてのアプリは、いつでもユーザーによって固定解除できます。 ユーザーのアプリをピン留めするには、クラウド アプリケーション管理者、Azure Active Directory のアプリケーション管理者、または Microsoft 365 のグローバル管理者である必要があります。 管理者ロールの詳細については、[Microsoft 365](../add-users/about-admin-roles.md) [の Azure AD 組み込みロール](/azure/active-directory/roles/permissions-reference)と管理者ロールに関するページを参照してください。 

アプリ起動ツールと Office.com の詳細については、[アプリ起動ツール](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)と[、office.com とOffice 365アプリ起動ツールに関するブログ記事の更新プログラムに関する](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)記事を参照してください。

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Azure Active Directory ポータルを使用してアプリをピン留めする

> [!NOTE]
> Microsoft 365 アプリは、アプリ起動ツールに既に表示されているため、この一覧から除外されます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> の Microsoft 365 管理センターに移動します。
2. 左側のナビゲーションで [**すべて表示**] を選択し、[**管理 センター**] で [**Azure Active Directory**] を選択します。
3. **Azure Active Directory** で、[**エンタープライズ アプリケーション** > **のユーザー設定**] を選択します。
4. **[Office 365設定]** セクションで、[**アプリケーションの追加**] を選択します。
5. ユーザーのアプリ起動ツールにピン留めするアプリケーションを選択し、[ **追加**] を選択します。

:::image type="content" source="../../media/add-apps.png" alt-text="アプリをピン留めするための Microsoft 365 の設定。":::

### <a name="pin-a-custom-app"></a>カスタム アプリをピン留めする

> [!NOTE]
> ユーザー インターフェイスは、この機能を使用するために追加の Azure AD ライセンスを購入する必要があるかどうかを示します。 詳細については、 [Azure Active Directory の価格に関するページを](https://azure.microsoft.com/pricing/details/active-directory/)参照してください。

1. **Azure Active Directory** で、[すべてのアプリケーション] ページの上部にある [**エンタープライズ アプリケーション** > ] の [**新しい****アプリケーション**] を選択します。
2. [ **アプリケーションの追加]** ページで、Azure Active Directory のプレビュー バージョンの場合は、[ **ギャラリー以外のアプリケーション** ] または [ **独自のアプリケーションの作成** ] を選択します。 
3. アプリケーションの名前を入力し、[ **ユーザーとグループ** ] タブにユーザーを割り当てます。
4. **[プロパティ**] タブを使用して、アプリのアイコンをアップロードします。
5. アプリに URL を割り当てるには、[ **シングル サインオン** ] タブで [ **リンク]** を選択し、URL を入力します。
6. **[保存]** を選択します。

## <a name="create-application-collections"></a>アプリケーション コレクションを作成する

また、組織内のユーザーのアプリケーション コレクションを作成することもできます。 手順については、[Azure portalのマイ アプリ ポータルでコレクションを作成する方法に関する記事を参照](/azure/active-directory/manage-apps/access-panel-collections)してください。