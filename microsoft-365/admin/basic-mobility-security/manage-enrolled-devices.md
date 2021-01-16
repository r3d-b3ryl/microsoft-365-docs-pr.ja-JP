---
title: Microsoft 365 のモバイル デバイス管理に登録されているデバイスを管理する
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
description: 基本的なモビリティとセキュリティは、モバイル デバイスのセキュリティ保護と管理に役立ちます。
ms.openlocfilehash: 4954da0ff44276d9bd46cabc78bc52c7879e5e26
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876962"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Microsoft 365 のモバイル デバイス管理に登録されているデバイスを管理する

Microsoft 365 の組み込みのモバイル デバイス管理は、iPhone、iPad、Android、Windows スマートフォンなど、ユーザーのモバイル デバイスをセキュリティで保護し、管理するのに役立ちます。 最初の手順では、Microsoft 365 にサインインし、Basic Mobility and Security をセットアップします。 詳細については [、「Basic Mobility and Security のセットアップ」を参照してください](set-up.md)。

セットアップ後、組織内のユーザーはデバイスをサービスに登録する必要があります。 詳細については [、「Basic Mobility and Security を使用してモバイル デバイスを登録する」を参照してください](enroll-your-mobile-device.md)。その後、Basic Mobility and Security を使用して、組織内のデバイスを管理できます。 たとえば、デバイス セキュリティ ポリシーを使用して、電子メール アクセスや他のサービスの制限、デバイス レポートの表示、デバイスのリモート ワイプを行えます。 通常、これらのタスクを実行するには、セキュリティ & コンプライアンス センターに移動します。 詳しくは [、Microsoft 365 コンプライアンス センターをご覧ください](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)。

## <a name="device-management-tasks"></a>デバイス管理タスク

デバイス管理パネルにアクセスするには、次の手順を実行します。

1.  [Microsoft 365 管理センターに移動します](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)。

2. 検索フィールドに「モバイル デバイス管理」と入力し、結果の一覧からモバイル デバイス管理   を選択します。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="モバイル デバイス管理オプション":::

3. [  **始めましょう] を選択します**。

## <a name="manage-mobile-devices"></a>モバイル デバイスの管理

Basic Mobility and Security をセットアップした後、組織内のモバイル デバイスを管理する方法を次に示します。

|**目的**|**説明**|
|:----------------|:------------------------------------------------------------------------------|
|デバイスをワイプする |[デバイス管理] パネルで **、デバイス名、[  **フル** ワイプ] の順に選択してすべての情報を削除するか、選択的ワイプを選択してデバイス上の組織情報     ****   のみを削除します。 詳細については [、「Basic Mobility and Security」の「モバイル デバイスをワイプする」を参照してください](wipe-mobile-device.md)。|
|サポートされていないデバイスによる Exchange ActiveSync を使用した Exchange メールへのアクセスをブロックする |[デバイス管理] パネルで、[ブロック] を選択  **します**。 |
|パスワードの要件やセキュリティ設定など、デバイス ポリシーを設定する |[デバイス管理] パネルで、[デバイス セキュリティ ポリシー **の追加**+ ]   >  **を選択します**。 詳しくは、「Basic Mobility and Security でのデバイス セキュリティ ポリシーの作成 [」をご覧ください](create-device-security-policies.md)。|
|ブロックされたデバイスの一覧を表示する  |[デバイス管理] パネルの [ビューの選択  **] で、[ブロック]**     **を選択します**。 |
|ユーザーまたはユーザーのグループに対して、準拠していない、またはサポートされていないデバイスのブロックを解除する  |デバイスのブロックを解除するには、次のいずれかを選択します。<br/>- ポリシーが適用されているセキュリティ グループからユーザーを削除します。 Microsoft 365 管理センターの [グループ] に> **し**、グループ名を選択します。 [メンバー **と管理者の編集] を選択します**。<br/>- ユーザーがメンバーであるセキュリティ グループをデバイス ポリシーから削除します。 セキュリティ センター コンプライアンス センター&セキュリティ > **デバイス セキュリティ**   >  **ポリシーに移動します**。 デバイス ポリシー名を選択し、[展開の編集]**を**  >  **選択します**。<br/>- デバイス ポリシーの準拠しないすべてのデバイスのブロックを解除します。 セキュリティ センター コンプライアンス センター&セキュリティ > **デバイス セキュリティ**   >  **ポリシーに移動します**。 デバイス ポリシー名を選択し、[アクセス **の要件の** 編集  >  **] を選択します**。 [アクセス  **とレポートの違反を許可する] を選択します**。<br/>- ユーザーまたはユーザーのグループの準拠していないデバイスまたはサポートされていないデバイスのブロックを解除するには、[セキュリティ & コンプライアンス センター >セキュリティ ポリシー] **** デバイス管理 デバイス アクセス設定の管理に移動します   >  ****   >  ****。 Microsoft 365 へのアクセスがブロックされるのを除外するメンバーを含むセキュリティ グループを追加します。 詳細については [、Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)管理センターでセキュリティ グループを作成、編集、または削除するを参照してください。|
|ユーザーを削除して、デバイスが Basic Mobility and Security によって管理されなくなった |ユーザーを削除するには、Basic Mobility and Security のデバイス管理ポリシーを持つセキュリティ グループを編集します。 詳細については  [、Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)管理センターでセキュリティ グループを作成、編集、または削除するを参照してください。<br/>すべての Microsoft 365 ユーザーから Basic Mobility and Security を削除するには、「Basic Mobility and Security をオフにする [」を参照してください](turn-off.md)。|

Live (v14)