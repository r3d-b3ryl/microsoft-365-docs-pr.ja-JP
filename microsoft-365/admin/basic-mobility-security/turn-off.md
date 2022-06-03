---
title: 基本的なモビリティとセキュリティをオフにする
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: グループまたはポリシーを削除して、基本的なモビリティとセキュリティを無効にします。
ms.openlocfilehash: 59a54b9969bf16c7523a6862c6f0960bb1527e8a
ms.sourcegitcommit: 1fa0b15f86470c49dddf0d6de59d553a38ae259b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65863034"
---
# <a name="turn-off-basic-mobility-and-security"></a>基本的なモビリティとセキュリティをオフにする

基本的なモビリティとセキュリティを効果的に無効にするには、デバイス管理ポリシーからセキュリティ グループによって定義されたユーザーのグループを削除するか、ポリシー自体を削除します。

- 作成したデバイス ポリシーからユーザー セキュリティ グループを削除して、ユーザーのグループを削除します。

- すべての Basic Mobility および Security デバイス ポリシーを削除して、すべてのユーザーの基本的なモビリティとセキュリティを無効にします。

これらのオプションを使用すると、組織内のデバイスに対する基本的なモビリティとセキュリティの適用が解除されます。 残念ながら、基本的なモビリティとセキュリティを設定した後は、単に "プロビジョニング解除" することはできません。

> [!IMPORTANT]
> ポリシーからユーザー セキュリティ グループを削除するか、ポリシー自体を削除すると、ユーザーのデバイスに与える影響に注意してください。 たとえば、デバイスによっては、電子メール プロファイルとキャッシュされた電子メールが削除される場合があります。 詳細については、「ポリシーを[削除するか、ポリシーからユーザーを削除するとどうなるか」を](../../admin/basic-mobility-security/create-device-security-policies.md)参照してください。

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Basic Mobility および Security デバイス ポリシーからユーザー セキュリティ グループを削除する

1. ブラウザーの種類: [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).

2. デバイス ポリシーを選択し、[ **ポリシーの編集]** を選択します。

3. **[展開]** ページで、[**削除**] を選択します。

4. [ **グループ]** で、セキュリティ グループを選択します。

5. [ **削除] を** 選択し、[保存] を選択 **します**。

## <a name="remove-basic-mobility-and-security-device-policies"></a>基本的なモビリティとセキュリティのデバイス ポリシーを削除する

1. ブラウザーの種類: [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).

2. デバイス ポリシーを選択し、[ポリシーの **削除**] を選択します。

3. [警告] ダイアログ ボックスで、[ **はい**] を選択します。

> [!NOTE]
> 組織のデバイスがまだブロック状態にある場合にデバイスのブロックを解除する手順の詳細については、ブログ記事「[Mobile Device Management for Office 365からのAccess Controlの削除](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)」を参照してください。
