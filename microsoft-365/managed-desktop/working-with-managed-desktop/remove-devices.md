---
title: デバイスの削除
description: Microsoft Managed Desktop 管理からデバイスを削除する
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893813"
---
# <a name="remove-devices"></a>デバイスの削除

管理ポータルを使用して、Microsoft Managed Desktop 管理からデバイスを削除できます。 このアクションは永続的ですが、登録手順に従って Microsoft Managed Desktop に再度 [登録できます](../get-started/register-devices-self.md)。

デバイスを削除すると、次のすべてが発生します。

- Autopilot からデバイスを削除します。
- すべての "モダン ワークプレース" デバイス グループからデバイスを削除します。
- 管理ポータルの [デバイス] **ブレード** からデバイスを削除します。

デバイスを削除する場合は、Azure Active Directory (Azure Active Directory) と Microsoft Intune からデバイスを削除ADオプションがあります。
 
> [!CAUTION]
> デバイスに関連するオブジェクトを Azure AD Microsoft Intune から削除すると、永続的です。 オブジェクトを削除すると、Intune および Azure ポータルからデバイスを表示または管理できません。 デバイスは会社の企業リソースにアクセスできません。 デバイスが削除された後にサインインしようとする場合、会社のデータが削除される可能性があります。

1. [Microsoft Endpoint Manager で、](https://endpoint.microsoft.com/)左側 **のナビゲーション ウィンドウで**[デバイス] を選択します。
2. メニューの **[Microsoft Managed Desktop]** セクションを探し、[デバイス] を **選択します**。
3. [Microsoft Managed Desktop Devices] ワークスペースで、削除するデバイスを選択します。
4. [ **デバイスの操作]** を選択し、[デバイスの **削除]** を選択して、フライインを開いてデバイスを削除します。
5. フライインで、選択したデバイスを確認し、[デバイスの削除] **を選択します**。 Azure オブジェクトと Intune オブジェクトAD同時に削除する場合は、チェック ボックスをオンにします。 デバイスの削除が完了するには数分かかる場合があります。

> [!NOTE]
> 保留中の登録状態にあるデバイス **は** 削除できません。