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
ms.openlocfilehash: 65d7647e9000152d2eeb8d6bf36e8d45a0d4fa90
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984702"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>管理ポータルで、管理者の連絡先を、追加および確認する

サービスが顧客とMicrosoft マネージド デスクトップする方法は複数あります。 コミュニケーションを合理化し、適切なユーザーと確認するには、一連の管理者連絡先を提供する必要があります。 Microsoft マネージド デスクトップIT 運用は、テナントのトラブルシューティングに関する問題について、これらのユーザーに問い合わせています。

> [!IMPORTANT]
> 管理ポータルにこれらの連絡先を既に追加している可能性があります。 その場合は、重大なインシデントが発生した場合Microsoft マネージド デスクトップ連絡先 **リストが正確** である必要があります。

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory管理ポータルMicrosoft マネージド デスクトップアクセス権

Microsoft マネージド デスクトップ管理ポータルでは、ポータルにアクセスするユーザーに次のいずれかの役割 (Azure Active Directory) AD必要があります。
- グローバル管理者
- Intune サービス管理者
- グローバル閲覧者
- サービス サポート管理者

グローバル管理者は、組織を登録する管理者である必要Microsoft マネージド デスクトップ。 5 つの役割はすべて、タスクを開始および表示するための管理ポータル内で同じアクセス権を持ちます。 Azure AD でこれらのロールを割り当てる方法の詳細については、「管理者ロールのアクセス許可」を[参照](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)Azure Active Directory。 

## <a name="admin-contact-areas-of-focus"></a>管理者の連絡先のフォーカス領域

管理者の連絡先は、質問に答え、さまざまな分野で決定を下す最適な人物またはグループである必要があります。 **Microsoft マネージド デスクトップ操作は、顧客が要求したサポート要求に関する質問について、これらの管理者の連絡先に連絡します。** これらの管理者の連絡先は、サポート要求の更新と新しいメッセージに関する通知を受け取る。 これらの領域には、次のものが含まれます。

フォーカス領域 | に関する質問
--- | ---
アプリのパッケージ化 | アプリのパッケージ化のトラブルシューティング
デバイス | デバイスの正常性、デバイスとデバイスMicrosoft マネージド デスクトップトラブルシューティング
セキュリティ | デバイスのセキュリティに関するMicrosoft マネージド デスクトップトラブルシューティング
IT ヘルプ デスク | サポートスタッフがサポートエリア外でユーザーチケットを引き渡Microsoft マネージド デスクトップ場合 
その他 | 他の領域でカバーされていない問題の場合

**これらの連絡先に対して選択するユーザーは、自分の環境に関する意思決定を行う知識と権限を持Microsoft マネージド デスクトップです。** アプリ環境をオンボードMicrosoft マネージド デスクトップ、ローカル のヘルプデスクとセキュリティの連絡先を追加するように求めるメッセージが表示されます。 

サポート要求を送信する場合は、 [管理者の連絡先が必要です](../service-description/support.md)。 サポート要求のフォーカス領域の管理者連絡先が必要です。 

**管理者連絡先を追加するには**

1.  サインインして [Microsoft エンドポイント マネージャー][をクリックします](https://endpoint.microsoft.com)。 

2.  [**テナントの管理]** で、[連絡先] セクションを探 **Microsoft マネージド デスクトップ[** 管理者連絡先]**を選択します**。 

3. **[追加]** を選択します。

4.  [フォーカスエリア **] を選択** し、連絡先の情報を入力します。 

    ![その他、アプリ、セキュリティなどのフォーカス領域の一覧](../../media/areaoffocus.png)

5. フォーカス領域ごとに繰り返します。 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>データの使用を開始するMicrosoft マネージド デスクトップ

1. 管理ポータルで管理者連絡先を追加して確認する (このトピック)
2. [条件付きアクセスを調整する](conditional-access.md)
3. [ライセンスを割り当てる](assign-licenses.md)
4. [Intune ポータル サイトをデバイスにインストールする](company-portal.md)
5. [Enterprise State Roaming を有効にする](enterprise-state-roaming.md)
6. [Microsoft マネージド デスクトップのデバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. [アプリをデバイスに展開する](deploy-apps.md)
