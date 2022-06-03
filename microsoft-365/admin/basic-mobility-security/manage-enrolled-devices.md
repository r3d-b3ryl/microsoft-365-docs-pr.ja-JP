---
title: Microsoft 365のモバイル デバイス管理に登録されているデバイスを管理する
f1.keywords:
- NOCSH
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
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- MET150
description: Microsoft 365にサインインし、Basic Mobility and Security を設定して、組み込みのモバイル デバイス管理を使用してユーザーのモバイル デバイスをセキュリティで保護および管理します。
ms.openlocfilehash: b84c97302743177f0a69978ebf358c0fbd1045a8
ms.sourcegitcommit: 1fa0b15f86470c49dddf0d6de59d553a38ae259b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65863568"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Microsoft 365のモバイル デバイス管理に登録されているデバイスを管理する

Microsoft 365用の組み込みのモバイル デバイス管理は、iPhone、iPad、Android、Windowsスマートフォンなどのユーザーのモバイル デバイスをセキュリティで保護して管理するのに役立ちます。 最初の手順では、Microsoft 365にサインインし、基本的なモビリティとセキュリティを設定します。 詳細については、「 [基本的なモビリティとセキュリティの設定](set-up.md)」を参照してください。

セットアップが完了したら、組織内のユーザーがサービスにデバイスを登録する必要があります。 詳細については、「 [Basic Mobility and Security を使用してモバイル デバイスを登録する」](enroll-your-mobile-device.md)を参照してください。 その後、Basic Mobility and Security を使用して、組織内のデバイスを管理できます。 たとえば、デバイス セキュリティ ポリシーを使用して、電子メール アクセスやその他のサービスの制限、デバイス レポートの表示、デバイスのリモートワイプを支援できます。 通常は、セキュリティ & コンプライアンス センターに移動して、これらのタスクを実行します。 詳細については、「[Microsoft Purview コンプライアンス ポータル](../../compliance/microsoft-365-compliance-center.md)」を参照してください。

## <a name="device-management-tasks"></a>デバイス管理タスク

デバイス管理パネルにアクセスするには、次の手順に従います。

1. Microsoft 365 管理センターにサインインし、[モバイル デバイス管理 ページ](https://portal.office.com/adminportal/home?#/MifoDevices)に移動します。

1. [ **始めましょう**] を選択します。

## <a name="manage-mobile-devices"></a>モバイル デバイスの管理

基本的なモビリティとセキュリティを設定したら、組織内のモバイル デバイスを管理する方法をいくつか示します。

|目的|説明|
|---|---|
|デバイスをワイプする|デバイス管理 パネルで *、デバイス名* を選択し、[**フル ワイプ**] を選択してすべての情報を削除するか、[**選択的ワイプ]** を選択してデバイス上の組織情報のみを削除します。 詳細については、「 [Basic Mobility and Security でモバイル デバイスをワイプする](wipe-mobile-device.md)」を参照してください。|
|サポートされていないデバイスによる Exchange ActiveSync を使用した Exchange メールへのアクセスをブロックする|デバイス管理 パネルで、[**ブロック**] を選択します。|
|パスワード要件やセキュリティ設定などのデバイス ポリシーを設定する|[デバイス管理] パネルで、[**デバイス セキュリティ ポリシー** > **の追加 +**] を選択します。 詳細については、「 [基本的なモビリティとセキュリティでデバイス セキュリティ ポリシーを作成する」を参照してください](create-device-security-policies.md)。|
|ブロックされたデバイスの一覧を表示する|[デバイス管理] パネルの [**ビューの選択]** で [ブロック] を選択 **します**。|
|ユーザーまたはユーザーのグループに対して、準拠していない、またはサポートされていないデバイスのブロックを解除する|デバイスのブロックを解除するには、次のいずれかを選択します。<br/>- ポリシーが適用されているセキュリティ グループからユーザーまたはユーザーを削除します。 Microsoft 365 管理センター > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**グループ**</a>に移動し、グループ名を選択します。 [ **メンバーと管理者の編集]** を選択します。<br/>- ユーザーがメンバーになっているセキュリティ グループをデバイス ポリシーから削除します。 セキュリティ & コンプライアンス センター > **セキュリティ ポリシー****デバイス セキュリティ ポリシー** > に移動します。 デバイス ポリシー名を選択し、[展開 **の編集]** >  を選択 **します**。<br/>- デバイス ポリシーに準拠していないすべてのデバイスのブロックを解除します。 セキュリティ & コンプライアンス センター > **セキュリティ ポリシー****デバイス セキュリティ ポリシー** > に移動します。 デバイス ポリシー名を選択し、[**アクセス要件****の編集]** を選択します > 。 [ **アクセスとレポート違反を許可する]** を選択します。<br/>- ユーザーまたはユーザーのグループの非準拠デバイスまたはサポートされていないデバイスのブロックを解除するには、セキュリティ & コンプライアンス センター>**セキュリティ ポリシー** > **デバイス管理デバイス****アクセス設定の管理** > に移動します。 Microsoft 365へのアクセスをブロックされないように除外するメンバーを含むセキュリティ グループを追加します。 詳細については、「[Microsoft 365 管理センターでセキュリティ グループを作成、編集、または削除する」を参照](../../admin/email/create-edit-or-delete-a-security-group.md)してください。|
|デバイスが Basic Mobility と Security によって管理されなくなったようにユーザーを削除する|ユーザーを削除するには、Basic Mobility and Security のデバイス管理ポリシーを持つセキュリティ グループを編集します。 詳細については、「[Microsoft 365 管理センターでセキュリティ グループを作成、編集、または削除する」を参照](../../admin/email/create-edit-or-delete-a-security-group.md)してください。<br/>すべてのMicrosoft 365 ユーザーから Basic Mobility と Security を削除するには、「[Basic Mobility and Security を無効にする](turn-off.md)」を参照してください。|

Live (v14)
