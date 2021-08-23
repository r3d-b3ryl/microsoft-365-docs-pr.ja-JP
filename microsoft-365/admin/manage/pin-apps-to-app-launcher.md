---
title: ユーザーのアプリ 起動ツールにアプリをピン留めする
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
ms.service: o365-administration
ms.custom: admindeeplinkMAC
localization_priority: Normal
description: グローバル管理者は、ユーザーのアプリ 起動ツールに最大 3 つのアプリをピン留めできます。
ms.openlocfilehash: b26f77d819f41517add59be14f26931f14001c65
ms.sourcegitcommit: a7b289b8cc3a2eb79d5e46f20f2968adc0237da1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58394470"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>ユーザーのアプリ 起動ツールにアプリをピン留めする

Azure Active Directory ポータルのコントロールを使用して、最大 3 つのアプリを Office.com に固定し、組織内のすべてのユーザーに対してアプリ 起動ツールをピン留めできます。 アプリケーションのグループを整理することもできます。 後で追加したアプリは、いつでもユーザーによって固定解除できます。 ユーザー用にアプリをピン留めするには、クラウド アプリケーション管理者か、Azure Active Directory のアプリケーション管理者、またはグローバル管理者である必要Office 365。 管理者ロールの詳細については、「[管理者ロール」](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)および「Azure Active Directoryの管理者ロール」[を参照](../add-users/about-admin-roles.md)Microsoft 365。 

アプリ 起動ツールと Office.com の詳細については、「アプリ[](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)起動ツールと office.com[](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)および Office 365 ランチャーのブログ記事を参照してください。

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>アプリをピン留Azure Active Directoryポータルを使用する

1. で、Microsoft 365 管理センターに移動します <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。
2. 左側のナビゲーションで、[すべて **表示]** を選択し、[管理センター] の下の **[管理** センター] で 、[Azure Active Directory]**を選択します**。
3. **[Azure Active Directory]** で、[アプリケーション **Enterprise設定]**  >  **を選択します**。
4. [アプリケーションの **追加Office 365 設定]** セクションで、[アプリケーションの追加]**を選択します**。
5. ユーザーのアプリ 起動ツールにピン留めするアプリケーションを選択し、[追加] を **選択します**。

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365設定を使用してアプリをピン留めします。":::

### <a name="pin-a-custom-app"></a>カスタム アプリのピン留め

> [!NOTE]
> ユーザー インターフェイスは、この機能を使用するために追加の Azure ADを購入する必要があるかどうかを示します。 詳細については、「価格の設定[Azure Active Directory参照してください](https://azure.microsoft.com/pricing/details/active-directory/)。

1. **[Azure Active Directory]** で、[すべての **Enterprise]** ページの上部にある [新しいアプリケーション] を  >  **選択** します。
2. [アプリケーションの **追加] ページ** で、[ギャラリー以外のアプリケーション] または [独自のアプリケーションを作成する] を選択します (プレビュー バージョンのアプリケーションを使用している場合Azure Active Directory。 
3. アプリケーションの名前を入力し、[ユーザーとグループ] タブで **ユーザーを割り当** てる。
4. [プロパティ **] タブ** を使用して、アプリのアイコンをアップロードします。
5. アプリに URL を割り当てるには、[シングル サインオン]タブで[リンク] を選択し、URL を入力します。
6. **[保存]** を選択します。

## <a name="create-application-collections"></a>アプリケーション コレクションの作成

また、組織内のユーザーのアプリケーション コレクションを作成することもできます。 手順については、「Azure portal の My Apps ポータルでコレクションを作成 [する」を参照してください](/azure/active-directory/manage-apps/access-panel-collections)。