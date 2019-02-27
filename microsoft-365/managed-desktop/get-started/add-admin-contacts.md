---
title: Microsoft Managed Desktop 管理ポータルで管理者の連絡先を追加する
description: フォーカスされている領域ごとに、連絡先の情報をお伝えください。
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 31984609681b6e3b1b6de9996eb8fb0fcf6f5624
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869178"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a>Microsoft Managed Desktop 管理ポータルで管理者の連絡先を追加する

Microsoft Managed Desktop service がお客様と通信するには、いくつかの方法があります。コミュニケーションを効率化して、最適な連絡先を確認するには、一連の管理者の連絡先を提供する必要があります。Microsoft マネージドデスクトップ IT 操作は、テナントの問題のトラブルシューティングについて、これらのユーザーに連絡します。 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Microsoft Managed Desktop 管理ポータルの Azure Active Directory アクセス

Microsoft Managed Desktop 管理ポータルでは、ポータルにアクセスするユーザーが次のいずれかの Azure Active Directory (AD) の役割を持っている必要があります。
- グローバル管理者
- Intune サービス管理者
- 課金管理者
- サービスサポート管理者

グローバル管理者は、Microsoft マネージドデスクトップにお客様を登録する必要があります。 すべての5つの役割は、タスクを開始して表示するために、管理ポータル内で同じアクセス権を持ちます。 これらの役割を azure AD に割り当てる方法の詳細については、「 [azure Active Directory での管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。 

## <a name="admin-contact-focus-areas"></a>管理者の連絡先のフォーカス領域

管理者の連絡先は、質問に回答したり、さまざまなフォーカスエリアの意思決定を行ったりできるベストのユーザーまたはグループである必要があります。 Microsoft マネージドデスクトップの操作は、お客様が提出したサポート要求に関する質問について、これらの管理者の連絡先に連絡します。 これらの管理者の連絡先は、サポート要求の更新と新しいメッセージに関する通知を受け取ります。 次のような領域があります。

フォーカスエリア | に関する質問
--- | ---
アプリ | アプリのパッケージ化のトラブルシューティング
[デバイス] | デバイスの正常性、Microsoft マネージドデスクトップデバイスのトラブルシューティング
セキュリティ | Microsoft マネージドデスクトップデバイスに関するセキュリティ上の問題のトラブルシューティング
その他 | 他の領域でカバーされない問題の場合

これらの連絡先に対して選択するユーザーは、Microsoft マネージドデスクトップ環境を決定するための知識と権限を持っている必要があります。Microsoft マネージドデスクトップ環境をオンにすると、ローカルのヘルプデスクおよびセキュリティのための連絡先を追加するように求められます。 

[サポートリクエストを送信](../working-with-managed-desktop/support.md)する場合は、管理者の連絡先が必要です。サポート要求のフォーカス領域に対する管理者の連絡先が必要です。 

**管理者の連絡先を追加するには**

1.  [Microsoft Managed Desktop 管理ポータル](http://aka.ms/mwaasportal)にサインインします。 

2.  [**サポート**] で、[管理者の**連絡先**] を選択します。 

    ![サポートメニュー、管理者の連絡先](images/admincontacts.png)

3. [**追加**] を選択します。

    ![管理ポータルの [追加] ボタン](images/adminadd.png)

4.  **フォーカスの領域**を選択し、連絡先の情報を入力します。 

    ![フォーカス領域のリスト](images/areaoffocus.png)

5. フォーカスの領域ごとに繰り返します。 

