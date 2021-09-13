---
title: デバイスの削除
description: デバイスを管理からMicrosoft マネージド デスクトップする
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
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215164"
---
# <a name="remove-devices"></a>デバイスの削除

管理ポータルを使用して、Microsoft マネージド デスクトップ管理からデバイスを削除できます。 このアクションは永続的ですが、登録手順に従って、Microsoft マネージド デスクトップに登録[できます](../get-started/register-devices-self.md)。

デバイスを削除すると、次のすべてが発生します。

- Autopilot からデバイスを削除します。
- すべての "モダン ワークプレース" デバイス グループからデバイスを削除します。
- 管理ポータルの [デバイス] **ブレード** からデバイスを削除します。

デバイスを削除すると、デバイスをデバイス (Azure AD) から削除Azure Active DirectoryオプションがMicrosoft Intune。
 
> [!CAUTION]
> デバイスに関連するオブジェクトを Azure ADから削除Microsoft Intune永続的です。 オブジェクトを削除すると、Intune および Azure ポータルからデバイスを表示または管理できません。 デバイスは会社の企業リソースにアクセスできません。 デバイスが削除された後にサインインしようとする場合、会社のデータが削除される可能性があります。

1. [[Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)で、左側 **のナビゲーション ウィンドウ** で [デバイス] を選択します。
2. メニューの **[Microsoft マネージド デスクトップ]** セクションを探し、[デバイス] を **選択します**。
3. [デバイスMicrosoft マネージド デスクトップ] ワークスペースで、削除するデバイスを選択します。
4. [ **デバイスの操作]** を選択し、[デバイスの **削除]** を選択して、フライインを開いてデバイスを削除します。
5. フライインで、選択したデバイスを確認し、[デバイスの削除] **を選択します**。 Azure オブジェクトと Intune オブジェクトAD同時に削除する場合は、チェック ボックスをオンにします。 デバイスの削除が完了するには数分かかる場合があります。

> [!NOTE]
> 保留中の登録状態にあるデバイス **は** 削除できません。