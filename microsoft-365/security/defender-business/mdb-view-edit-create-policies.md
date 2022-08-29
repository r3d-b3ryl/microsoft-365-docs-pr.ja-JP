---
title: Microsoft Defender for Businessでポリシーを表示または編集する
description: Defender for Business でサイバーセキュリティ ポリシーを表示、編集、作成、削除する方法について説明します。 セキュリティ ポリシーを使用してデバイスを保護します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: a7281605f4bc47c2ce39ef3b067a5db39aa33142
ms.sourcegitcommit: 9b10e56b9e83f3a80757fa6108bebd1d80cf4178
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67319935"
---
# <a name="view-or-edit-policies-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでポリシーを表示または編集する

Defender for Business では、デバイスに適用されるポリシーを使用してセキュリティ設定を構成します。 Defender for Business には、セットアップと構成のエクスペリエンスを簡素化するために、会社のデバイスがオンボードされるとすぐに保護できるように、事前に構成されたポリシーが含まれています。 既定のポリシーを使用したり、ポリシーを編集したり、独自のポリシーを作成したりできます。

**この記事では、次の方法について説明します**。

- [既定のポリシーの概要を確認する](#default-policies-in-defender-for-business)
- [既存のポリシーを表示する](#view-your-existing-policies)
- [既存のポリシーを編集する](#edit-an-existing-policy)
- [新しいポリシーの作成](#create-a-new-policy)

> [!NOTE]
> この記事の手順では、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) でセキュリティ ポリシーを表示、編集、および作成する方法について説明します。 Microsoft Intuneを使用している場合は、「[Microsoft Intuneでエンドポイント のセキュリティを管理](/mem/intune/protect/endpoint-security)する」を参照してください。

## <a name="default-policies-in-defender-for-business"></a>Defender for Business の既定のポリシー

Defender for Business には、会社のデバイスを保護するためのポリシーの主な種類が 2 つあります。

- **次世代保護ポリシー**: Microsoft Defender ウイルス対策やその他の脅威に対する保護機能の構成方法を決定します
- **ファイアウォール ポリシー**。会社のデバイスとの間のフローが許可されているネットワーク トラフィックを決定する

## <a name="view-your-existing-policies"></a>既存のポリシーを表示する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。 

2. ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。ポリシーは、オペレーティング システム (**[Windows クライアント]** など) とポリシーの種類 (**[次世代保護]** や **[ファイアウォール]** など) ごとに分類されています。 

3. オペレーティング システムのタブ (**[Windows クライアント]** など) を選択し、**[次世代保護]** と **[ファイアウォール]** のカテゴリでポリシーの一覧を確認します。 

4. ポリシーの詳細を表示するには、その名前を選択します。 サイド ウィンドウが開き、そのポリシーに関する詳細情報 (そのポリシーで保護されているデバイスなど) が表示されます。

## <a name="edit-an-existing-policy"></a>既存のポリシーを編集する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。 

2. ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。ポリシーは、オペレーティング システム (**[Windows クライアント]** など) とポリシーの種類 (**[次世代保護]** や **[ファイアウォール]** など) ごとに分類されています。 

3. オペレーティング システムのタブ (**[Windows クライアント]** など) を選択し、**[次世代保護]** と **[ファイアウォール]** のカテゴリでポリシーの一覧を確認します。 

4. ポリシーを編集するには、その名前を選択し、**[編集**] を選択します。

5. **[全般情報]** タブで情報を確認します。 必要に応じて、説明を編集できます。 **[次へ]** を選択します。

6. **[デバイス グループ]** タブで、このポリシーを受け取るデバイス グループを決定します。  

   - 選択したデバイス グループをそのままにするには、**[次へ]** を選択します。
   - ポリシーからデバイス グループを削除するには、**[削除]** を選択 します。
   - 新しいデバイス グループを設定するには、**[新しいグループの作成]** を選択し、デバイス グループを設定します。 (このタスクに関するヘルプについては、「 [Defender for Business のデバイス グループ」を](mdb-create-edit-device-groups.md)参照してください)。
   - ポリシーを別のデバイス グループに適用するには、**[既存のグループを使用]** を選択します。

   ポリシーを受け取るデバイス グループを指定したら、**[次へ]** を選択します。

7. **[構成の設定]** タブで設定を確認します。 必要に応じて、ポリシーの設定を編集できます。 このタスクのヘルプについては、次の記事を参照してください。 

   - [次世代の構成設定を理解する](mdb-next-gen-configuration-settings.md)   
   - [ファイアウォールの設定](mdb-firewall.md)

   次世代の保護設定を指定したら、**[次へ]** を選択します。

8. **[ポリシーの確認]** タブで、一般情報、対象デバイス、および構成設定を確認します。 

   - **[編集]** を選択して、必要な変更を加えます。
   - 続行する準備ができたら、[ **ポリシーの更新**] を選択します。

## <a name="create-a-new-policy"></a>新しいポリシーの作成

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。 

2. ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。ポリシーは、オペレーティング システム (**[Windows クライアント]** など) とポリシーの種類 (**[次世代保護]** や **[ファイアウォール]** など) ごとに分類されています。 

3. オペレーティング システムのタブ (**[Windows クライアント]** など) を選択し、**[次世代保護]** ポリシーの一覧を確認します。 

4. **[次世代保護]** または **[ファイアウォール]** で、**[+ 追加]** を選択します。

5. **[全般情報]** タブで次の手順を実行します。

   1. 名前と説明を入力します。この情報は、後で自分とチームがポリシーを特定するのに役立ちます。
   2. ポリシーの順序を確認し、必要に応じて編集します。 (詳細については、「[ポリシーの順序](mdb-policy-order.md)」を参照してください)。
   3. **次へ** を選択します。 

7. **[デバイス グループ]** タブで、新しいデバイス グループを作成するか、既存のグループを使用します。 ポリシーは、デバイス グループを介してデバイスに割り当てられます。 留意事項がいくつかあります。

   - 最初は、会社のユーザーが会社のデータと電子メールへのアクセスに使用しているデバイスを含む既定のデバイス グループのみを使用できます。 既定のデバイス グループを残して使用することができます。
   - 既定のポリシーとは異なる特定の設定でポリシーを適用するには、新しいデバイス グループを作成します。 
   - デバイス グループを設定するときは、オペレーティング システムのバージョンなど、特定の条件を指定します。 条件を満たすデバイスは、除外しない限り、そのデバイス グループに含まれます。 
   - すべてのすべてのデバイス グループ (定義した既定のデバイス グループおよびカスタム デバイス グループを含みます) は、Azure Active Directory (Azure AD) に格納されます。

   デバイス グループの詳細については、「 [Defender for Business のデバイス グループ」を](mdb-create-edit-device-groups.md)参照してください。

8. **[構成設定]** タブで、ポリシーの設定を指定し、**[次へ]** を選択します。 個々の設定の詳細については、「 [Defender for Business の構成設定」を](mdb-next-gen-configuration-settings.md)参照してください。

9. **[ポリシーの確認]** タブで、一般情報、対象デバイス、および構成設定を確認します。 

   - **[編集]** を選択して、必要な変更を加えます。
   - 続行する準備ができたら、[ **ポリシーの作成**] を選択します。


## <a name="next-steps"></a>次の手順

次のタスクのうち 1 つ以上を選択します。

- [デバイスの管理](mdb-manage-devices.md)
- [Defender for Business で新しいポリシーを作成する](mdb-create-new-policy.md)
- [Defender for Business でインシデントを表示および管理する](mdb-view-manage-incidents.md)
- [Defender for Business の脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)