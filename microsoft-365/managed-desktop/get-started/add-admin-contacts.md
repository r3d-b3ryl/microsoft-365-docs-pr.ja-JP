---
title: 管理ポータルで、管理者の連絡先を、追加および確認する
description: フォーカス領域ごとに問い合わせ先を教えて下さい。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925894"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>管理ポータルで、管理者の連絡先を、追加および確認する

Microsoft Managed Desktop サービスが顧客と通信する方法は複数あります。 コミュニケーションを合理化し、適切なユーザーと確認するには、一連の管理者連絡先を提供する必要があります。 Microsoft Managed Desktop IT Operations は、テナントのトラブルシューティングに関する問題についてこれらのユーザーに問い合わせています。

> [!IMPORTANT]
> 管理ポータルにこれらの連絡先を既に追加している可能性があります。 その場合は、重大なインシデントが発生した場合に Microsoft Managed **Desktop** が連絡先リストにアクセスできる必要がありますので、連絡先リストが正確か確認してください。

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Microsoft Managed Desktop Admin ポータルの Azure Active Directory アクセス

Microsoft Managed Desktop Admin ポータルでは、ポータルにアクセスするユーザーが次の Azure Active Directory (AD) の役割のいずれかを持っている必要があります。
- グローバル管理者
- Intune サービス管理者
- グローバル閲覧者
- サービス サポート管理者

組織を Microsoft Managed Desktop に登録するには、グローバル管理者が必要です。 5 つの役割はすべて、タスクを開始および表示するための管理ポータル内で同じアクセス権を持ちます。 Azure Active Directory でのこれらのロールの割り当てAD詳細については [、「Administrator role permissions in Azure Active Directory」を参照してください](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 

## <a name="admin-contact-areas-of-focus"></a>管理者の連絡先のフォーカス領域

管理者の連絡先は、質問に答え、さまざまな分野で決定を下す最適な人物またはグループである必要があります。 **Microsoft Managed Desktop Operations は、お客様から送信されたサポート要求に関する質問について、管理者の連絡先に問い合わせします。** これらの管理者の連絡先は、サポート要求の更新と新しいメッセージに関する通知を受け取る。 これらの領域には、次のものが含まれます。

フォーカス領域 | に関する質問
--- | ---
アプリのパッケージ化 | アプリのパッケージ化のトラブルシューティング
デバイス | デバイスの正常性、Microsoft Managed Desktop デバイスでのトラブルシューティング
セキュリティ | Microsoft Managed Desktop デバイスに関するセキュリティの問題のトラブルシューティング
IT ヘルプ デスク | Microsoft Managed Desktop サポート領域外でサポート スタッフがユーザー チケットを引き渡す場合 
その他 | 他の領域でカバーされていない問題の場合

**これらの連絡先を選択するユーザーは、Microsoft Managed Desktop 環境に関する意思決定を行う知識と権限を持っている必要があります。** Microsoft Managed Desktop 環境をオンボードすると、ローカルのヘルプデスクとセキュリティの連絡先を追加するように求めるメッセージが表示されます。 

サポート要求を送信する場合は、 [管理者の連絡先が必要です](../service-description/support.md)。 サポート要求のフォーカス領域の管理者連絡先が必要です。 

**管理者連絡先を追加するには**

1.  [Microsoft Managed Desktop 管理ポータルにサインインします](https://aka.ms/mwaasportal)。 

2.  [サポート **] で**、[管理者連絡先] **を選択します**。 

    ![[サポート] メニューの [選択した上部の近くの管理者の連絡先]](../../media/admincontacts.png)

3. **[追加]** を選択します。

    ![[エクスポートと更新] の左側にある管理ポータルの [追加] ボタン](../../media/adminadd.png)

4.  [フォーカスエリア **] を選択** し、連絡先の情報を入力します。 

    ![その他、アプリ、セキュリティなどのフォーカス領域の一覧](../../media/areaoffocus.png)

5. フォーカス領域ごとに繰り返します。 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop の使用を開始する手順

1. 管理ポータルで管理者連絡先を追加して確認する (このトピック)
2. [条件付きアクセスを調整する](conditional-access.md)
3. [ライセンスを割り当てる](assign-licenses.md)
4. [Intune ポータル サイトをデバイスにインストールする](company-portal.md)
5. [Enterprise State Roaming を有効にする](enterprise-state-roaming.md)
6. [Microsoft マネージド デスクトップのデバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. [アプリをデバイスに展開する](deploy-apps.md)