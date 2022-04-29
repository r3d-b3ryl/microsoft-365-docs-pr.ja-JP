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
description: 組み込みの Basic Mobility と Security を使用して、登録済みデバイスから情報を削除します。
ms.openlocfilehash: 959e785958dd6d447713507ee9c48763b814db78
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65129092"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a>Basic Mobility and Security でモバイル デバイスをワイプする

組み込みの Basic Mobility and Security for Microsoft 365を使用すると、組織の情報のみを削除したり、出荷時のリセットを実行してモバイル デバイスからすべての情報を削除し、出荷時設定に復元したりできます。

## <a name="before-you-begin"></a>開始する前に

モバイル デバイスは、組織の機密情報を格納し、組織のMicrosoft 365 リソースへのアクセスを提供できます。 組織の情報を保護するために、会社のデータをファクトリ リセットまたは削除できます。

- **出荷時設定へのリセット**: インストールされているアプリケーション、写真、個人情報など、ユーザーのモバイル デバイス上のすべてのデータを削除します。 ワイプが完了すると、デバイスは出荷時の設定に復元されます。

- **会社のデータを削除** する: 組織のデータのみを削除し、インストールされているアプリケーション、写真、個人情報をユーザーのモバイル デバイスに残します。

- **デバイスがワイプされると (Factory Reset or Remove Company Data)**、デバイスは管理対象デバイスの一覧から削除されます。

- **デバイスを自動的にリセット** する: ユーザーが特定の回数だけデバイス パスワードの入力に失敗した後にデバイスを自動的に工場出荷時設定にリセットする Basic Mobility および Security ポリシーを設定できます。 これを行うには、「 [基本的なモビリティとセキュリティでデバイス セキュリティ ポリシーを作成する」の手順に](create-device-security-policies.md)従います。

- デバイスをワイプするときに **ユーザー エクスペリエンスを把握する場合** は、「[ユーザーとデバイスの影響は何ですか?](#whats-the-user-and-device-impact)」を参照してください。

## <a name="wipe-a-mobile-device"></a>モバイル デバイスをワイプする

1. [Microsoft 365 管理センター](../../admin/admin-overview/admin-center-overview.md)に戻ります。

2. 検索フィールドに「モバイル デバイス管理」と入力し、結果の一覧から **[モバイル デバイス管理**] を選択します。

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Basic Mobility および Secruity モバイル デバイス管理オプション。":::

3. [ **デバイスの管理**] を選択します。

4. ワイプを実行するデバイスを選びます。

5. [ **管理**] を選択します。

6. 実行するリモートワイプのタイプを選択します。

    - 完全ワイプを実行し、デバイスを工場出荷時の設定に復元するには、[ **出荷時のリセット**] を選択します。
    - 組織の情報のみを選択的にワイプして削除するには、[**会社のデータ** Microsoft 365の削除] を選択します。
    - 組織からデバイスを削除するには、[デバイスの **削除**] を選択します。

7. [**はい**] を選択して確認します。

## <a name="how-do-i-know-it-worked"></a>操作方法機能したことを知っていますか?

マネージド デバイスの一覧にモバイル デバイスが表示されなくなりました。

## <a name="why-would-you-want-to-wipe-a-device"></a>デバイスをワイプする理由

次の理由でデバイスをワイプします。

- スマートフォンやタブレットなどのモバイル デバイスは、常にフル機能を備えています。 つまり、ユーザーは個人識別や機密通信などの機密情報を保存し、外出先でアクセスする方が簡単です。 これらのモバイル デバイスのいずれかが紛失または盗難にあった場合、デバイスをワイプすると、組織の情報が間違った手に渡らないようにすることができます。
- ユーザーが Basic Mobility and Security に登録されている個人用デバイスを使用して組織を離れた場合、工場出荷時の設定へのリセットを実行することで、組織情報がそのユーザーと共に行かないようにすることができます。
- 組織がユーザーにモバイル デバイスを提供している場合は、デバイスを随時再割り当てすることが必要になる場合があります。 新しいユーザーに割り当てる前にデバイスで Factory Reset を実行すると、前の所有者の機密情報が確実に削除されます。

## <a name="whats-the-user-and-device-impact"></a>ユーザーとデバイスの影響は何ですか?

ワイプはすぐにモバイル デバイスに送信され、デバイスは Azure Active Directory で非準拠としてマークされます。 デバイスが出荷時の既定値にリセットされると、すべてのデータが削除されますが、次の表では、会社のデータを削除するときにデバイスがデバイスの種類ごとに削除される内容について説明します。

|コンテンツへの影響|iOS|Android|
|---|---|---|
|Microsoft 365アプリデータは、デバイスが Intune App Protection ポリシーによって保護されている場合にワイプされます。 アプリは削除されません。 モバイル アプリケーション管理 (MAM) ポリシーで保護されていないデバイスの場合、OutlookとOneDriveはキャッシュされたデータを削除しません。<br/>**メモ** Intune アプリ保護 ポリシーを適用するには、Intune ライセンスが必要です。|はい|はい|
|Basic Mobility と Security によってデバイスに適用されるポリシー設定は適用されなくなりました。ユーザーは設定を変更できます。|はい|はい|
|Basic Mobility と Security によって作成された電子メール プロファイルは削除され、デバイス上のキャッシュされた電子メールは削除されます。|はい|該当なし|

> [!NOTE]
> ポータル サイトアプリは、iOS および Android デバイス用 Play ストアのApp Storeで利用できます。
