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
ms.openlocfilehash: 3bb9bfe55653b021ce5a86dd5d3dbc3de45ed19a
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876830"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Basic Mobility and Security でモバイル デバイスをワイプする

Microsoft 365 の組み込みの Basic Mobility and Security を使用して、組織の情報のみを削除したり、出荷時の設定にリセットしてモバイル デバイスからすべての情報を削除し、出荷時の設定に復元することができます。

## <a name="before-you-begin"></a>はじめに

モバイル デバイスは、組織の機密情報を保存し、組織の Microsoft 365 リソースへのアクセスを提供できます。 組織の情報を保護するために、出荷時のリセットまたは会社データの削除を行います。

- **工場出荷時の** 設定へのリセット: インストールされているアプリケーション、写真、個人情報など、ユーザーのモバイル デバイス上のすべてのデータを削除します。 ワイプが完了すると、デバイスは出荷時の設定に復元されます。

- **会社のデータを** 削除する : 組織データのみを削除し、インストールされているアプリケーション、写真、個人情報をユーザーのモバイル デバイスに残します。

- **デバイスがワイプされると (出荷時** のリセットまたは会社データの削除)、管理対象デバイスの一覧からデバイスが削除されます。
    
- **デバイスを自動的** にリセットする : Basic Mobility and Security ポリシーを設定できます。このポリシーは、ユーザーが特定の回数、デバイス パスワードの入力に失敗した後にデバイスを自動的に出荷時にリセットします。 これを行うには、「基本的なモビリティとセキュリティでのデバイス セキュリティ ポリシーの作成」の [手順に従います](create-device-security-policies.md)。
    
- **デバイスをワイプするときにユーザー エクスペリエンス** を知りたい場合は、「ユーザーとデバイスの影響   [について」を参照してください](#whats-the-user-and-device-impact)。

## <a name="wipe-a-mobile-device"></a>モバイル デバイスをワイプする

1.  [Microsoft 365 管理センターに移動します](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)。

2. 検索フィールドに「モバイル デバイス管理」と入力し、結果の一覧からモバイル デバイス管理を選択します。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="モバイル デバイスの基本的なモビリティと分離の管理オプション":::

3. [デバイス **の管理] を選択します**。

4. ワイプを実行するデバイスを選びます。

5. [管理] **を選択します**。

6. 実行するリモートワイプのタイプを選択します。

    - フル ワイプを実行し、デバイスを出荷時の設定に戻す場合は、[出荷時の設定にリセット] **を選択します**。
    - 選択的ワイプを実行し、Microsoft 365 組織情報のみを削除するには、[会社データの削除] を **選択します**。
    - 組織からデバイスを削除するには、[デバイスの削除] **を選択します**。

7. [**はい**] を選択して確認します。

## <a name="how-do-i-know-it-worked"></a>動作を知る方法

管理対象デバイスの一覧にモバイル デバイスが表示されなくなりました。

## <a name="why-would-you-want-to-wipe-a-device"></a>デバイスをワイプする理由

次の理由でデバイスをワイプします。

- スマートフォンやタブレットなどのモバイル デバイスは、機能がフル機能を備えつながっています。 つまり、ユーザーは個人識別や機密通信などの会社の機密情報を保存し、その情報に移動する方が簡単です。 これらのモバイル デバイスの 1 つを紛失または盗難した場合、デバイスをワイプすると、組織の情報が誤った手で終わるのを防ぐのに役立ちます。
- ユーザーが Basic Mobility and Security に登録されている個人用デバイスを使用して組織を離れる場合、工場出荷時の設定へのリセットを実行することで、組織の情報がユーザーと一緒に行かされるのを防ぐのに役立ちます。
- 組織でモバイル デバイスをユーザーに提供する場合は、デバイスの再割り当てが必要になる場合があります。 デバイスを新しいユーザーに割り当てる前に、デバイスで工場出荷時の設定にリセットを実行すると、前の所有者からの機密情報が確実に削除されます。

## <a name="whats-the-user-and-device-impact"></a>ユーザーとデバイスに与える影響

ワイプはすぐにモバイル デバイスに送信され、デバイスは Azure Active Directory で非準拠としてマークされます。 デバイスが出荷時の既定値にリセットされると、すべてのデータが削除されます。次の表は、デバイスが会社のデータを削除するときにデバイスの種類ごとに削除されるコンテンツを示しています。

|**コンテンツの不可能性**|**iOS 10 以降**|**Android 5 以降**|
|:-----|:-----|:-----|
|デバイスが Intune App Protection ポリシーで保護されている場合、Microsoft 365 アプリのデータはワイプされます。 アプリは削除されません。 モバイル アプリケーション管理 (MAM) ポリシーで保護されていないデバイスの場合、Outlook と OneDrive はキャッシュされたデータを削除できません。<br/>**注** Intune アプリ保護ポリシーを適用するには、Intune ライセンスが必要です。|はい|はい|
|Basic Mobility and Security によってデバイスに適用されるポリシー設定は適用されなくなりました。ユーザーは設定を変更できます。|はい|はい|
|Basic Mobility and Security によって作成された電子メール プロファイルが削除され、デバイス上のキャッシュされた電子メールが削除されます。|はい|該当なし|
>[!NOTE]
>ポータル サイト アプリは、iOS 用アプリ ストアと Android デバイス用 Play ストアで利用できます。

## <a name="related-topics"></a>関連項目

[基本的なモビリティとセキュリティの設定](set-up.md)