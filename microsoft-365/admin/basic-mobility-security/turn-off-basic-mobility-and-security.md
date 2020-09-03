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
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: グループまたはポリシーを削除して、基本のモビリティとセキュリティをオフにします。
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336962"
---
# <a name="turn-off-basic-mobility-and-security"></a>基本的なモビリティとセキュリティをオフにする

基本的なモビリティとセキュリティを効果的に無効にするには、デバイス管理ポリシーからセキュリティグループによって定義されたユーザーのグループを削除するか、ポリシー自体を削除します。

- 作成したデバイスポリシーからユーザーセキュリティグループを削除して、ユーザーのグループを削除します。
    
- すべての基本的なモビリティとセキュリティデバイスポリシーを削除することによって、すべてのユーザーの基本的なモビリティとセキュリティを無効にします。
    
これらのオプションは、組織内のデバイスの基本的なモビリティとセキュリティの適用を削除します。 残念ながら、セットアップ後に基本的なモビリティとセキュリティを単に "準備解除" することはできません。 

>[!IMPORTANT]
>ユーザーのセキュリティグループをポリシーから削除したり、ポリシー自体を削除したりすると、ユーザーのデバイスに与える影響に注意してください。 たとえば、電子メールプロファイルやキャッシュされたメールは、デバイスによっては削除されることがあります。 詳細については、「  [ポリシーを削除するか、ポリシーからユーザーを削除するとどうなりますか?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact) 」を参照してください。

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>基本的なモビリティとセキュリティデバイスポリシーからユーザーセキュリティグループを削除する

1. ブラウザーで、次のように入力  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) します。

2. デバイスポリシーを選択し、[ **ポリシーの編集**] を選択します。 

3. [  **展開**   ] ページで、[ **削除**] を選択します。
    
4. [  **グループ**] で、セキュリティグループを選択します。

5. [  **削除**] を選択し、[ **保存**] を選択します。
    

## <a name="remove-basic-mobility-and-security-device-policies"></a>基本的なモビリティとセキュリティデバイスポリシーを削除する

1.  ブラウザーで、次のように入力  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) します。 

2.  デバイスポリシーを選択し、[  **ポリシーの削除**] を選択します。
    
3.  警告ダイアログボックスで、[ **はい]** を選択します。

>[!NOTE] 
>組織のデバイスがまだブロックされている状態である場合にデバイスのブロックを解除する手順の詳細については、ブログ投稿「 [Office 365 のモバイルデバイス管理からのアクセス制御の削除](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)」を参照してください。
