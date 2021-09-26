---
title: 基本的なモビリティとセキュリティをオフにする
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
description: グループまたはポリシーを削除して、Basic Mobility and Security をオフにします。
ms.openlocfilehash: 730c927c01bb7103c61694749ec7d55ec381a39a
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2021
ms.locfileid: "59775086"
---
# <a name="turn-off-basic-mobility-and-security"></a>基本的なモビリティとセキュリティをオフにする

Basic Mobility and Security を効果的にオフにするには、セキュリティ グループによって定義されたユーザーのグループをデバイス管理ポリシーから削除するか、ポリシー自体を削除します。

- 作成したデバイス ポリシーからユーザー セキュリティ グループを削除して、ユーザーのグループを削除します。

- すべての Basic Mobility および Security デバイス ポリシーを削除して、すべてのユーザーに対して基本モビリティとセキュリティを無効にします。

これらのオプションを使用すると、組織内のデバイスに対する Basic Mobility と Security の適用が削除されます。 残念ながら、基本モビリティとセキュリティをセットアップした後は、単に "プロビジョニング解除" を行う必要があります。

> [!IMPORTANT]
> ポリシーからユーザー セキュリティ グループを削除したり、ポリシー自体を削除したりすると、ユーザーのデバイスに与える影響に注意してください。 たとえば、デバイスによっては、メール プロファイルとキャッシュされたメールが削除される場合があります。 詳細については、「ポリシーを削除するか、ポリシーからユーザーを削除するとどう  [なるか」を参照してください。](../../admin/basic-mobility-security/create-device-security-policies.md)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Basic Mobility および Security デバイス ポリシーからユーザー セキュリティ グループを削除する

1. ブラウザーの種類:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) です。

2. デバイス ポリシーを選択し、[ポリシーの編集 **] を選択します**。

3. [展開]  **ページで**   、[削除] を **選択します**。

4. [グループ  **] で**、セキュリティ グループを選択します。

5. [削除  **] を選択** し、[保存] **を選択します**。

## <a name="remove-basic-mobility-and-security-device-policies"></a>基本モビリティおよびセキュリティ デバイス ポリシーの削除

1. ブラウザーの種類:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) です。

2. デバイス ポリシーを選択し、[ポリシーの削除]  **を選択します**。

3. [警告] ダイアログ ボックスで、[はい] を **選択します**。

> [!NOTE]
> 組織のデバイスがまだブロック状態にある場合にデバイスのブロックを解除する手順については、ブログの投稿「アクセス制御をブロックから削除する」を[参照Mobile Device Management for Office 365。](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)
