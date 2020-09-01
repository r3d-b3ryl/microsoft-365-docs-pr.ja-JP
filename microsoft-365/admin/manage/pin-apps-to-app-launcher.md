---
title: ユーザーのアプリ起動ツールにアプリを固定する
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
description: グローバル管理者として、最大3つのアプリをユーザーのアプリ起動ツールにピン留めすることができます。
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310877"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>ユーザーのアプリ起動ツールにアプリを固定する

Azure Active Directory ポータルのコントロールを使用して、Office.com に最大3つのアプリと、組織内のすべてのユーザーのアプリ起動ツールをピン留めできます。 アプリケーションのグループを整理することもできます。 追加したアプリは、いつでもユーザーが後で固定解除できるようになります。 ユーザーに対してアプリを固定するには、Cloud application administrator または Azure Active Directory のアプリケーション管理者、または Office 365 の全体管理者である必要があります。 管理者の役割の詳細については、「 [Microsoft 365 の](../add-users/about-admin-roles.md)「 [Azure Active Directory の管理役割](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」と「管理者の役割」を参照してください。 

アプリ起動ツールおよび Office.com の詳細については、「 [アプリ起動ツール](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) と [更新プログラムについて office.com」および「Office 365 アプリ起動ツール](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) 」のブログ記事を参照してください。

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>Azure Active Directory ポータルを使用してアプリを固定する

1. Microsoft 365 管理センター () に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> します。
2. 左側のナビゲーションで [ **すべて表示**] を選択し、[ **管理センター**] の下の [ **Azure Active Directory**] を選択します。
3. [ **Azure Active Directory**] で、[**エンタープライズアプリケーション**  >  **ユーザー設定**] を選択します。
4. [ **Office 365 の設定** ] セクションで、[ **アプリケーションの追加**] を選択します。
5. ユーザーのアプリ起動ツールにピン留めするアプリケーションを選択し、[ **追加**] を選択します。

:::image type="content" source="../../media/add-apps.png" alt-text="アプリを固定するための Microsoft 365 設定。":::

### <a name="pin-a-custom-app"></a>カスタムアプリを固定する

> [!NOTE]
> この機能を使用するには、追加の Azure AD ライセンスを購入する必要があるかどうかを示すユーザーインターフェイスが表示されます。 詳細については、「 [Azure Active Directory の料金](https://azure.microsoft.com/pricing/details/active-directory/)」を参照してください。

1. **Azure Active Directory**で、[すべての**Enterprise applications**  >  **アプリケーション**] ページの上部にある [エンタープライズアプリケーション**新しいアプリケーション**] を選択します。
2. [ **アプリケーションの追加** ] ページで、プレビュー版の Azure Active Directory を使用している場合は、[ **ギャラリー以外のアプリケーション** ] または [独自のアプリケーションを **作成** する] を選択します。 
3. アプリケーションの名前を入力し、[ユーザー **とグループ** ] タブでユーザーを割り当てます。
4. [ **プロパティ** ] タブを使用して、アプリのアイコンをアップロードします。
5. アプリに URL を割り当てるには、[ **シングルサインオン** ] タブで、[ **リンク** ] を選択し、url を入力します。
6. **[保存]** を選択します。

## <a name="create-application-collections"></a>アプリケーションコレクションを作成する

組織内のユーザーのアプリケーションコレクションを作成することもできます。 手順については、「 [Azure portal の個人用アプリポータルでコレクションを作成する](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections)」を参照してください。