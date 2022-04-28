---
title: デバイス保護ポリシーを表示または編集する
description: Microsoft 365 Business Premium でデバイス保護ポリシーを表示、編集、作成、削除する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/14/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: high
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 816b425fbbd511b68d2c21f313b497bbd4b77f8a
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65087033"
---
# <a name="view-and-edit-your-device-protection-policies"></a>デバイス保護ポリシーを表示および編集する

Microsoft 365 Business Premium では、管理対象デバイスのセキュリティ設定は、デバイス保護ポリシーを使用して構成されます。 セットアップと構成のエクスペリエンスを簡素化できるよう、組織のデバイスがオンボードされ次第すぐに保護することを可能にする、事前構成済みのポリシーが用意されています。 既定のポリシーを使用するか、既存のポリシーを編集するか、独自のポリシーを作成します。

**このガイドでは、次の内容を説明します:**

- 既定のポリシーの概要を確認する
- 既存のポリシーを表示する
- 既存のポリシーを編集する
- 新しいポリシーの作成

## <a name="default-device-protection-policies"></a>既定のデバイス保護ポリシー

Microsoft 365 Business Premium には、組織のデバイスを保護するための主なポリシーとして、次の 2 種類が含まれています。

- **次世代保護ポリシー**: Microsoft Defender ウイルス対策やその他の脅威に対する保護機能の構成方法を決定します

- **ファイアウォール ポリシー**: 組織のデバイスとの間のフローが許可されるネットワーク トラフィックを決定します

これらのポリシーは、Microsoft 365 Business Premium サブスクリプションに含まれている Microsoft Defender for Business の一部です。

## <a name="view-your-existing-device-protection-policies"></a>既存のデバイス保護ポリシーを表示する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。 

2. ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。 ポリシーは、オペレーティング システム (**[Windows クライアント]** など) とポリシーの種類 (**[次世代保護]** や **[ファイアウォール]** など) ごとに分類されています。 

    :::image type="content" source="../media/mdb-deviceconfiguration.png" lightbox="../media/mdb-deviceconfiguration.png" alt-text="[デバイスの構成] ページ。":::

3. オペレーティング システムのタブ (**[Windows クライアント]** など) を選択し、**[次世代保護]** と **[ファイアウォール]** のカテゴリでポリシーの一覧を確認します。 

4. ポリシーの詳細を表示するには、その名前を選択します。 サイド ウィンドウが開き、そのポリシーに関する詳細情報 (そのポリシーで保護されているデバイスなど) が表示されます。

   :::image type="content" source="../media/mdb-deviceconfig-selectedpolicy.png" lightbox="../media/mdb-deviceconfig-selectedpolicy.png" alt-text="[デバイスの構成] ページで選択されたポリシーのスクリーンショット。":::

## <a name="edit-an-existing-device-protection-policy"></a>既存のデバイス保護ポリシーを編集する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。 

2. ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。 ポリシーは、オペレーティング システム (**[Windows クライアント]** など) とポリシーの種類 (**[次世代保護]** や **[ファイアウォール]** など) ごとに分類されています。 

3. オペレーティング システムのタブ (**[Windows クライアント]** など) を選択し、**[次世代保護]** と **[ファイアウォール]** のカテゴリでポリシーの一覧を確認します。 

4. ポリシーを編集するには、その名前を選択し、**[編集**] を選択します。

5. **[全般情報]** タブで情報を確認します。 必要に応じて、説明を編集できます。 **[次へ]** を選択します。

6. **[デバイス グループ]** タブで、このポリシーを受け取るデバイス グループを決定します。  

   - 選択したデバイス グループをそのままにするには、**[次へ]** を選択します。
   - ポリシーからデバイス グループを削除するには、**[削除]** を選択 します。
   - 新しいデバイス グループを設定するには、**[新しいグループの作成]** を選択し、デバイス グループを設定します。 (このタスクに関するヘルプについては、「[Microsoft 365 Business Premium のデバイス グループ](m365bp-device-groups-mdb.md)」を参照してください。)
   - ポリシーを別のデバイス グループに適用するには、**[既存のグループを使用]** を選択します。

   ポリシーを受け取るデバイス グループを指定したら、**[次へ]** を選択します。

7. **[構成の設定]** タブで設定を確認します。 必要に応じて、ポリシーの設定を編集できます。 このタスクのヘルプについては、次の記事を参照してください。 

   - [次世代の構成設定を理解する](../security/defender-business/mdb-next-gen-configuration-settings.md)   
   - [ファイアウォールの設定](../security/defender-business/mdb-firewall.md)

   次世代の保護設定を指定したら、**[次へ]** を選択します。

8. **[ポリシーの確認]** タブで、一般情報、対象デバイス、および構成設定を確認します。 

   - **[編集]** を選択して、必要な変更を加えます。
   - 続行する準備ができたら、**[ポリシーの更新]** を選択します。

## <a name="create-a-new-device-protection-policy"></a>新しいデバイス保護ポリシーを作成する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動し、サインインします。 

2. ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。 ポリシーは、オペレーティング システム (**[Windows クライアント]** など) とポリシーの種類 (**[次世代保護]** や **[ファイアウォール]** など) ごとに分類されています。 

3. オペレーティング システムのタブ (**[Windows クライアント]** など) を選択し、**[次世代保護]** ポリシーの一覧を確認します。 

4. **[次世代保護]** または **[ファイアウォール]** で、**[+ 追加]** を選択します。

5. **[全般情報]** タブで次の手順を実行します。

   1. 名前と説明を入力します。 この情報は、後で自分とチームがポリシーを特定するのに役立ちます。
   2. ポリシーの順序を確認し、必要に応じて編集します。 (詳細については、「[ポリシーの順序](../security/defender-business/mdb-policy-order.md)」を参照してください)。
   3. **次へ** を選択します。 

7. **[デバイス グループ]** タブで、新しいデバイス グループを作成するか、既存のグループを使用します。 ポリシーは、デバイス グループを介してデバイスに割り当てられます。 留意事項がいくつかあります。

   - 最初は、組織内のユーザーが組織のデータと電子メールにアクセスするために使用しているデバイスが含まれている、既定のデバイス グループのみが提供されている場合があります。 既定のデバイス グループを残して使用することができます。
   - 既定のポリシーとは異なる特定の設定でポリシーを適用するには、新しいデバイス グループを作成します。 
   - デバイス グループを設定するときは、オペレーティング システムのバージョンなど、特定の条件を指定します。 条件を満たすデバイスは、除外しない限り、そのデバイス グループに含まれます。 
   - すべてのすべてのデバイス グループ (定義した既定のデバイス グループおよびカスタム デバイス グループを含みます) は、Azure Active Directory (Azure AD) に格納されます。

   デバイス グループの詳細については、「[Microsoft Defender for Business のデバイス グループ](../security/defender-business/mdb-create-edit-device-groups.md)」を参照してください。

8. **[構成設定]** タブで、ポリシーの設定を指定し、**[次へ]** を選択します。 個々の設定の詳細については、「[Microsoft Defender for Business の次世代構成設定について理解する](../security/defender-business/mdb-next-gen-configuration-settings.md)」を参照してください。

9. **[ポリシーの確認]** タブで、一般情報、対象デバイス、および構成設定を確認します。 

   - **[編集]** を選択して、必要な変更を加えます。
   - 続行する準備ができたら、**[ポリシーの作成]** を選択します。

## <a name="next-objective"></a>次の目標

[デバイス グループ](m365bp-device-groups-mdb.md)の作成と管理。

