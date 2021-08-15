---
title: Basic Mobility and Security でモバイル デバイスをワイプする
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
description: 組み込みの Basic Mobility and Security を使用して、登録済みデバイスから情報を削除します。
ms.openlocfilehash: e8e5f9327a2145bcaaa5415e4d269de5ae351d2500838f5b2c972418041c218a
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53826584"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Basic Mobility and Security でモバイル デバイスをワイプする

Microsoft 365 の組み込みの Basic Mobility and Security を使用して、組織情報のみを削除したり、出荷時のリセットを実行してモバイル デバイスからすべての情報を削除し、工場出荷時の設定に復元することができます。

## <a name="before-you-begin"></a>はじめに

モバイル デバイスは、機密性の高い組織情報を保存し、組織のリソースにアクセスMicrosoft 365できます。 組織の情報を保護するために、出荷時のリセットまたは会社データの削除を行います。

- **出荷時の** リセット: インストールされているアプリケーション、写真、個人情報など、ユーザーのモバイル デバイス上のすべてのデータを削除します。 ワイプが完了すると、デバイスは工場出荷時の設定に復元されます。

- **会社のデータを削除** する: 組織データのみを削除し、ユーザーのモバイル デバイスにインストールされているアプリケーション、写真、および個人情報を残します。

- **デバイスがワイプされると (出荷** 時のリセットまたは会社のデータの削除)、デバイスは管理対象デバイスの一覧から削除されます。
    
- **デバイスを自動的** にリセットする: ユーザーがデバイス パスワードを特定の回数入力しようとして失敗した後、デバイスを自動的に出荷時にリセットする Basic Mobility and Security ポリシーを設定できます。 これを行うには、「基本モビリティとセキュリティでデバイス セキュリティ ポリシーを [作成する」の手順に従います](create-device-security-policies.md)。
    
- **デバイスをワイプするときにユーザー エクスペリエンス** を知りたい場合は、「ユーザーとデバイスの影響   [について」を参照してください](#whats-the-user-and-device-impact)。

## <a name="wipe-a-mobile-device"></a>モバイル デバイスをワイプする

1. [ファイル] に移動 [Microsoft 365 管理センター。](../../admin/admin-overview/about-the-admin-center.md)

2. [モバイル デバイスの管理] を検索フィールドに入力し、結果の一覧から [モバイル デバイス **の管理** ] を選択します。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="基本モビリティと Secruity モバイル デバイス管理オプション":::

3. [デバイス **の管理] を選択します**。

4. ワイプを実行するデバイスを選びます。

5. [管理 **] を選択します**。

6. 実行するリモートワイプのタイプを選択します。

    - フル ワイプを実行し、デバイスを工場出荷時の設定に復元するには、[出荷時のリセット] **を選択します**。
    - 組織情報のみを選択的にワイプして削除するには、[Microsoft 365削除]**を選択します**。
    - 組織からデバイスを削除するには、[デバイスの削除] **を選択します**。

7. [**はい**] を選択して確認します。

## <a name="how-do-i-know-it-worked"></a>どのように機能したのか?

管理対象デバイスの一覧にモバイル デバイスが表示されなくなりました。

## <a name="why-would-you-want-to-wipe-a-device"></a>デバイスをワイプする理由

次の理由でデバイスをワイプします。

- スマートフォンやタブレットなどのモバイル デバイスは、多くの場合、フル機能になりつつある。 つまり、ユーザーは、個人識別や機密通信などの機密情報を保存し、移動中にアクセスする方が簡単です。 これらのモバイル デバイスの 1 つが紛失または盗難に遭った場合、デバイスをワイプすると、組織の情報が間違った手で終わるのを防ぐのに役立ちます。
- ユーザーが Basic Mobility and Security に登録されている個人用デバイスを使用して組織を離れる場合、工場出荷時の状態にリセットを実行することで、組織の情報がユーザーと一緒に行かされるのを防ぐのに役立ちます。
- 組織がユーザーにモバイル デバイスを提供している場合は、デバイスを一度に再割り当てする必要があります。 デバイスを新しいユーザーに割り当てる前にデバイスで出荷時のリセットを実行すると、以前の所有者からの機密情報が確実に削除されます。

## <a name="whats-the-user-and-device-impact"></a>ユーザーとデバイスに与える影響

ワイプはモバイル デバイスに直ちに送信され、デバイスは Azure Active Directory で非準拠としてマークされます。 デバイスが出荷時の既定値にリセットされると、すべてのデータが削除されます。次の表は、デバイスが会社のデータを削除するときにデバイスの種類ごとに削除されるコンテンツを示しています。

|**コンテンツへの影響**|**iOS 10 以降**|**Android 5 以降**|
|:-----|:-----|:-----|
|Microsoft 365 Intune アプリ保護ポリシーでデバイスが保護されている場合、アプリ データはワイプされます。 アプリは削除されません。 モバイル アプリケーション管理 (MAM) ポリシーで保護されていないデバイスの場合、OutlookとOneDriveデータは削除されません。<br/>**メモ** Intune アプリ保護ポリシーを適用するには、Intune ライセンスが必要です。|はい|はい|
|Basic Mobility と Security によってデバイスに適用されるポリシー設定は適用されなくなりました。ユーザーは設定を変更できます。|はい|はい|
|Basic Mobility and Security によって作成されたメール プロファイルが削除され、デバイス上のキャッシュされたメールが削除されます。|はい|該当なし|

> [!NOTE]
> ポータル サイトアプリは、iOS 用アプリ ストアと Android デバイス向け Play ストアで利用できます。
