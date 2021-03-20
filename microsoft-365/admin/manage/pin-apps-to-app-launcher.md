---
title: ユーザーのアプリ 起動ツールにアプリをピン留めする
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: グローバル管理者は、ユーザーのアプリ 起動ツールに最大 3 つのアプリをピン留めできます。
ms.openlocfilehash: 965fcbbb3f0e22074e3f6c5476d65ade98fea94c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915220"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>ユーザーのアプリ 起動ツールにアプリをピン留めする

Azure Active Directory ポータルのコントロールを使用すると、最大 3 つのアプリをピン留 Office.com、組織内のすべてのユーザーに対してアプリ 起動ツールを固定できます。 アプリケーションのグループを整理することもできます。 後で追加したアプリは、いつでもユーザーによって固定解除できます。 ユーザー用にアプリをピン留めするには、クラウド アプリケーション管理者、または Azure Active Directory のアプリケーション管理者、または 365 のグローバル管理者Office必要があります。 管理者ロールの詳細については [、「Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) の管理者ロール」および [「Microsoft 365 の管理者ロール」を参照してください](../add-users/about-admin-roles.md)。 

アプリ 起動ツールとアプリ 起動ツールの詳細 Office.com、[](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)アプリ 起動ツールと office.com および[Office 365](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)アプリ 起動ツールのブログ記事を参照してください。

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Azure Active Directory ポータルを使用してアプリをピン留めする

1. で Microsoft 365 管理センターに移動します <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。
2. 左側のナビゲーションで、[すべて表示] **を** 選択し、[ **管理** センター] で **[Azure Active Directory] を選択します**。
3. **Azure Active Directory で、[** エンタープライズ アプリケーション] **[ユーザー設定**  >  **] を選択します**。
4. **[365 Office] セクションで、[** アプリケーションの追加]**を選択します**。
5. ユーザーのアプリ 起動ツールにピン留めするアプリケーションを選択し、[追加] を **選択します**。

:::image type="content" source="../../media/add-apps.png" alt-text="アプリをピン留めする Microsoft 365 の設定。":::

### <a name="pin-a-custom-app"></a>カスタム アプリのピン留め

> [!NOTE]
> ユーザー インターフェイスは、この機能を使用するために追加の Azure ADを購入する必要があるかどうかを示します。 詳細については [、「Azure Active Directory の価格」を参照してください](https://azure.microsoft.com/pricing/details/active-directory/)。

1. **Azure Active Directory で、[** すべてのアプリケーション]**ページ** の上部にある [エンタープライズ アプリケーション] [新  >  **しいアプリケーション] を選択** します。
2. [アプリケーションの **追加] ページ** で、[ギャラリー以外のアプリケーション] または [独自のアプリケーションを作成する] を選択します (プレビュー バージョンの Azure Active Directory を使用している場合)。 
3. アプリケーションの名前を入力し、[ユーザーとグループ] タブで **ユーザーを割り当** てる。
4. [プロパティ **] タブ** を使用して、アプリのアイコンをアップロードします。
5. アプリに URL を割り当てるには、[シングル サインオン]タブで[リンク] を選択し、URL を入力します。
6. **[保存]** を選択します。

## <a name="create-application-collections"></a>アプリケーション コレクションの作成

また、組織内のユーザーのアプリケーション コレクションを作成することもできます。 手順については、「Azure portal の My Apps ポータルでコレクションを作成 [する」を参照してください](/azure/active-directory/manage-apps/access-panel-collections)。