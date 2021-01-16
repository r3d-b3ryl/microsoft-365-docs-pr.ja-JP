---
title: Basic Mobility and Security をオフにする
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Basic Mobility and Security をオフにするグループまたはポリシーを削除します。
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876842"
---
# <a name="turn-off-basic-mobility-and-security"></a>Basic Mobility and Security をオフにする

Basic Mobility and Security を効果的にオフにするには、セキュリティ グループによって定義されたユーザーのグループをデバイス管理ポリシーから削除するか、ポリシー自体を削除します。

- 作成したデバイス ポリシーからユーザー セキュリティ グループを削除して、ユーザーのグループを削除します。

- すべての Basic Mobility and Security デバイス ポリシーを削除して、すべてのユーザーに対して Basic Mobility and Security を無効にします。

これらのオプションを使用すると、組織内のデバイスに対する Basic Mobility and Security の適用が削除されます。 残念ながら、Basic Mobility and Security をセットアップした後は、単に"準備を解除" する必要があります。 

>[!IMPORTANT]
>ポリシーからユーザー セキュリティ グループを削除したり、ポリシー自体を削除したりすると、ユーザーのデバイスに与える影響に注意してください。 たとえば、デバイスによっては、メール プロファイルとキャッシュされたメールが削除される場合があります。 詳しくは、「ポリシーを削除した場合、またはポリシーからユーザーを削除した場合の問題  [」をご覧ください。](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Basic Mobility and Security デバイス ポリシーからユーザー セキュリティ グループを削除する

1. ブラウザーで次の種類を入力します  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。

2. デバイス ポリシーを選択し、[ポリシーの編集 **] を選択します**。 

3. [展開]  **ページで**   、[削除] を **選択します**。

4. [  **グループ] で**、セキュリティ グループを選択します。

5. [削除  **] を選択** し、[保存] を **選択します**。

## <a name="remove-basic-mobility-and-security-device-policies"></a>Basic Mobility and Security デバイス ポリシーを削除する

1.  ブラウザーで次の種類を入力します  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) 。 

2.  デバイス ポリシーを選択し、[ポリシーの削除]  **を選択します**。
    
3.  [警告] ダイアログ ボックスで、[はい] を **選択します**。

>[!NOTE]
>組織のデバイスがまだブロック状態にある場合にデバイスのブロックを解除する手順については、Office [365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)のモバイル デバイス管理からのアクセス制御の削除に関するブログ投稿を参照してください。
