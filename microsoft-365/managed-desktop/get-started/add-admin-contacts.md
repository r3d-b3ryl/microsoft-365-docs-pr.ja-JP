---
title: 管理ポータルで管理者の連絡先を追加して確認する
description: フォーカスされている領域ごとに、連絡先の情報をお伝えください。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 3f77a5f6f0af83ea82d2ab3cea0798b95e27c2d2
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012068"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>管理ポータルで管理者の連絡先を追加して確認する

Microsoft Managed Desktop service がお客様と通信するには、いくつかの方法があります。 コミュニケーションを効率化し、適切な人物との関係を確認するには、一連の管理者の連絡先を提供する必要があります。 Microsoft マネージドデスクトップ IT 操作は、テナントの問題のトラブルシューティングについて、これらのユーザーに連絡します。

> [!IMPORTANT]
> これらの連絡先は、管理ポータルに既に追加されている場合があります。 その場合は、Microsoft 管理デスクトップが深刻なインシデントが発生した場合に、連絡先リストが正確**であること**を、すぐに確認してください。

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Microsoft Managed Desktop 管理ポータルの Azure Active Directory アクセス

Microsoft Managed Desktop 管理ポータルでは、ポータルにアクセスするユーザーが次のいずれかの Azure Active Directory (AD) の役割を持っている必要があります。
- グローバル管理者
- Intune サービス管理者
- 課金管理者
- サービスサポート管理者

グローバル管理者は、組織を Microsoft マネージドデスクトップに登録するためのものである必要があります。 すべての5つの役割は、タスクを開始して表示するために、管理ポータル内で同じアクセス権を持ちます。 これらの役割を Azure AD に割り当てる方法の詳細については、「 [Azure Active Directory での管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。 

## <a name="admin-contact-areas-of-focus"></a>フォーカスのある管理者の連絡先領域

管理者の連絡先は、質問に回答したり、フォーカスの異なる領域を決定するための最適なユーザーまたはグループである必要があります。 **Microsoft マネージドデスクトップの操作は、お客様が提出したサポート要求に関する質問について、これらの管理者の連絡先に連絡します。** これらの管理者の連絡先は、サポート要求の更新と新しいメッセージに関する通知を受け取ります。 次のような領域があります。

フォーカスの領域 | に関する質問
--- | ---
アプリのパッケージ化 | アプリのパッケージ化のトラブルシューティング
デバイス | デバイスの正常性、Microsoft マネージドデスクトップデバイスのトラブルシューティング
セキュリティ | Microsoft マネージドデスクトップデバイスに関するセキュリティ上の問題のトラブルシューティング
IT ヘルプデスク | サポートスタッフが Microsoft マネージドデスクトップサポート領域外のエンドユーザーのチケットを渡している場合は、 
Other | 他の領域でカバーされない問題の場合

**これらの連絡先に対して選択するユーザーは、Microsoft マネージドデスクトップ環境を決定するための知識と権限を持っている必要があります。** Microsoft マネージドデスクトップ環境をオンにすると、ローカルのヘルプデスクおよびセキュリティのための連絡先を追加するように求められます。 

[サポートリクエストを送信](../working-with-managed-desktop/support.md)する場合は、管理者の連絡先が必要です。 サポート要求のフォーカス領域に対する管理者の連絡先が必要です。 

**管理者の連絡先を追加するには**

1.  [Microsoft Managed Desktop 管理ポータル](https://aka.ms/mwaasportal)にサインインします。 

2.  [**サポート**] で、[管理者の**連絡先**] を選択します。 

    ![サポートメニュー、管理者の連絡先](images/admincontacts.png)

3. **[追加]** を選択します。

    ![管理ポータルの [追加] ボタン](images/adminadd.png)

4.  **フォーカスの領域**を選択し、連絡先の情報を入力します。 

    ![フォーカス領域のリスト](images/areaoffocus.png)

5. フォーカスの領域ごとに繰り返します。 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップの使用を開始する手順

1. 管理ポータルで管理者の連絡先を追加および確認する (このトピック)
2. [条件付きアクセスを調整する](conditional-access.md)
3. [ライセンスを割り当てる](assign-licenses.md)
4. [デバイスに Intune ポータルサイトをインストールする](company-portal.md)
5. [エンタープライズ状態の移動を有効にする](enterprise-state-roaming.md)
6. [Microsoft マネージドデスクトップデバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. [アプリをデバイスに展開する](deploy-apps.md)