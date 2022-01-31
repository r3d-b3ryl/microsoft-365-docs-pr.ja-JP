---
title: デバイスの削除
description: Microsoft Managed Desktop 管理からデバイスを削除する
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: c4be03b7ba86449a875e268adbbdfbf1d4625aab
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2022
ms.locfileid: "62281401"
---
# <a name="remove-devices"></a>デバイスの削除

管理ポータルを使用して、Microsoft Managed Desktop 管理からデバイスを削除できます。 このアクションは永続的ですが、登録手順に従って Microsoft Managed Desktop に再度 [登録できます](../get-started/register-devices-self.md)。

デバイスを削除すると、次のすべてが発生します。

- Autopilot からデバイスを削除します。
- すべての "モダン ワークプレース" デバイス グループからデバイスを削除します。
- 管理ポータルの [デバイス] **ブレード** からデバイスを削除します。

デバイスを削除する場合は、デバイスを削除Azure Active Directory (Azure AD) から削除Microsoft Intune。
  
> [!CAUTION]
> デバイスに関連するオブジェクトをデバイスから削除Azure AD、Microsoft Intune永続的です。 オブジェクトを削除すると、Intune および Azure ポータルからデバイスを表示または管理できません。 デバイスは会社の企業リソースにアクセスできません。 デバイスが削除された後にサインインしようとする場合、会社のデータが削除される可能性があります。

**デバイスを削除するには、次の方法を実行します。**

1. [[Microsoft エンドポイント マネージャー](https://endpoint.microsoft.com/)] で、左側 **のナビゲーション ウィンドウ** で [デバイス] を選択します。
2. [ **Microsoft Managed Desktop] セクションで、[** デバイス] を **選択します**。
3. **[Microsoft Managed Desktop Devices] ワークスペースで、** 削除するデバイスを選択します。
4. [ **デバイスの操作]** を選択し、[デバイスの **削除] を** 選択して、フライインを開いてデバイスを削除します。
5. フライインで、選択したデバイスを確認し、[デバイスの削除] **を選択します**。 また、アプリオブジェクトと Intune オブジェクトAzure AD同時に削除する場合は、チェック ボックスをオンにします。 デバイスの削除が完了するには数分かかる場合があります。

> [!NOTE]
> 保留中の登録状態にあるデバイス **は** 削除できません。
