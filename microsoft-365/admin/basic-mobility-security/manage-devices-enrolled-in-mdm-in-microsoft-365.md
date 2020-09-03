---
title: Microsoft 365 でモバイルデバイス管理に登録されているデバイスを管理する
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 基本的なモビリティとセキュリティは、モバイルデバイスをセキュリティで保護し、管理するのに役立ちます。
ms.openlocfilehash: 36ea0d12becca2e97a56aceea107fa1f5bf6ded4
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336975"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Microsoft 365 でモバイルデバイス管理に登録されているデバイスを管理する

Microsoft 365 の組み込みモバイルデバイス管理は、iPhones、Ipad、Androids、Windows phone などのユーザーのモバイルデバイスをセキュリティで保護し、管理するのに役立つ情報を示しています。 最初の手順として、Microsoft 365 にサインインし、基本的なモビリティとセキュリティを設定します。 詳細については、「 [基本モビリティとセキュリティを設定](set-up-basic-mobility-and-security.md)する」を参照してください。

設定した後は、組織内のユーザーがサービスにデバイスを登録する必要があります。 詳細については、「 [Basic Mobility And Security を使用してモバイルデバイスを登録する](enroll-your-mobile-device-using-basic-mobility-and-security.md)」を参照してください。その後、基本的なモビリティとセキュリティを使用して、組織内のデバイスの管理に役立てることができます。 たとえば、デバイスのセキュリティポリシーを使用して、電子メールアクセスまたはその他のサービスを制限したり、デバイスを表示したり、デバイスをリモートでワイプしたりすることができます。 通常、これらのタスクを実行するには、セキュリティ & コンプライアンスセンターに移動します。 詳細については、「 [Microsoft 365 コンプライアンスセンター](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)」を参照してください。

## <a name="device-management-tasks"></a>デバイス管理タスク

[デバイス管理] パネルを表示するには、次の手順を実行します。

1.  [Microsoft 365 管理センター](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)に移動します。
    
2. [検索] フィールドに「モバイルデバイスの管理」と入力し、結果の一覧から [**モバイルデバイスの管理**] を選択し   ます。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="モバイルデバイス管理オプション":::

3. [  **デバイスの管理**] を選択します。

## <a name="manage-mobile-devices"></a>モバイル デバイスの管理
    
基本的なモビリティとセキュリティを設定した後、組織内のモバイルデバイスを管理する方法について説明します。

|**目的**|**説明**|
|:----------------|:------------------------------------------------------------------------------|
|デバイスをワイプする |[デバイス管理] パネルで、[ *デバイス名*] を選択し、[  **フルワイプ**] を選択して   すべての情報を削除するか、または  **Selective wipe**   デバイス上の組織情報のみを削除するように選択してワイプします。 詳細については、「 [Basic Mobility And Security でモバイルデバイスをワイプする](wipe-mobile-device.md)」を参照してください。|
|サポートされていないデバイスによる Exchange ActiveSync を使用した Exchange メールへのアクセスをブロックする |[デバイス管理] パネルで、[  **ブロック**] を選択します。 |
|パスワードの要件やセキュリティ設定などのデバイスポリシーを設定する |[デバイスの管理] パネルで、[**デバイスセキュリティポリシー**の   >  **追加 +**] を選択します。 詳細については、「 [Create device security policies In Basic Mobility And security](create-device-security-policies-in-basic-mmobility-and-security.md)」を参照してください。|
|ブロックされたデバイスの一覧を表示する  |[デバイス管理] パネルの [  **ビューの選択**] で [     **ブロック**] を選択します。 |
|ユーザーまたはユーザーのグループに対して、準拠していない、またはサポートされていないデバイスのブロックを解除する  |デバイスのブロックを解除するには、次のいずれかを選択します。<br/>-ポリシーが適用されているセキュリティグループからユーザーを削除します。 Microsoft 365 管理センター > **グループ**に移動し、[グループ名] を選択します。 [ **メンバーと管理者の編集**] を選択します。<br/>-ユーザーがメンバーになっているセキュリティグループをデバイスポリシーから削除します。 [セキュリティ & コンプライアンスセンター > **セキュリティポリシー**] [   >  **デバイスセキュリティポリシー**] に移動します。 [デバイスポリシー名] を選択し、[展開の**編集**] を選択し  >  **Deployment**ます。<br/>-デバイスポリシーに準拠していないデバイスをすべてブロック解除します。 [セキュリティ & コンプライアンスセンター > **セキュリティポリシー**] [   >  **デバイスセキュリティポリシー**] に移動します。 [デバイスポリシー名] を選択**Edit**し、[  >  **アクセス要件**の編集] を選択します。 [  **アクセスを許可する] と [レポート違反**] を選択します。<br/>-ユーザーまたはユーザーグループに対して、準拠していないまたはサポートされていないデバイスのブロックを解除するには、[セキュリティ & コンプライアンスセンター > **セキュリティポリシー**] [   >  **デバイス管理**の管理] [   >  **デバイスアクセス設定の管理**] に移動します。 Microsoft 365 へのブロックアクセスから除外するメンバーを含むセキュリティグループを追加します。 詳細については、「 [Microsoft 365 管理センターでセキュリティグループを作成、編集、または削除する](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)」を参照してください。|
|組織内のデバイスに関する詳細を取得する  |どのデバイスが登録されていて、デバイスのセキュリティポリシーに準拠しているかなどの詳細については、「 [基本的なモビリティおよびセキュリティ管理デバイスに関する詳細を取得](get-details-about-basic-mobility-and-security-managed-devices.md)する」を参照してください。|
|基本的なモビリティとセキュリティによってデバイスが管理されなくなるようにユーザーを削除する |ユーザーを削除するには、基本的なモビリティとセキュリティのためのデバイス管理ポリシーを持つセキュリティグループを編集します。 詳細については、「  [Microsoft 365 管理センターでセキュリティグループを作成、編集、または削除する](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)」を参照してください。<br/>すべての Microsoft 365 ユーザーから基本的なモビリティとセキュリティを削除するには、「 [基本的なモビリティとセキュリティをオフ](turn-off-basic-mobility-and-security.md)にする」を参照してください。|

Live (v14)