---
title: Microsoft 365 Business Premium でのデバイス グループの操作
description: デバイス グループと、Microsoft 365 Business Premium で Intune でポリシーを適用する方法について説明し、サイバー攻撃からの保護を強化します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.localizationpriority: high
ms.date: 07/19/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: cde398c0ee13b7c06be3e0158b4f993476348b3d
ms.sourcegitcommit: c1eaea74c8ffce2f9f477c9469342e88e4a70c14
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2022
ms.locfileid: "66893966"
---
# <a name="device-groups-and-categories-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premium のデバイス グループとカテゴリ

Microsoft 365 Business Premium には、Microsoft Defender for Business と Microsoft Intune によるエンドポイント保護が含まれています。 デバイス保護ポリシーは、デバイス グループと呼ばれる特定のコレクションを通じてデバイスに適用されます。 Intune では、デバイスは別の整理方法としてデバイス カテゴリにグループ化されます。 

この記事に含まれるセクションは次のとおりです。  

- [デバイス グループの操作](#working-with-device-groups)
- [新しいデバイス グループを作成する方法](#create-a-device-group-in-the-microsoft-365-defender-portal)
- [ Intune で新しいデバイス カテゴリを作成する方法](#create-a-device-category-in-intune)

## <a name="working-with-device-groups"></a>デバイス グループの操作

デバイス グループは、オペレーティング システムのバージョンなど、特定の指定された条件のためにグループ化されたデバイスのコレクションです。 条件を満たすデバイスは、除外しない限り、そのデバイス グループに含まれます。

Microsoft 365 Business Premium では、使用できる既定のデバイス グループがあります。 既定のデバイス グループには、Defender for Business にオンボードされているすべてのデバイスが含まれます。 ただし、特定のデバイスに特定の設定を持つデバイス保護ポリシーを割り当てるために、新しいデバイス グループを作成することもできます。

既定のデバイス グループと定義したカスタム デバイス グループを含むすべてのデバイス グループは、[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis) (Azure AD) に格納されます。

## <a name="create-a-device-group-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルでデバイス グループを作成する

デバイス保護ポリシーの作成中または編集中に、新しいデバイス グループを作成できます。

1. [Microsoft 365 Defender ポータル](https://security.microsoft.com) に移動してサインインします。

2. ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。

3. 次のどちらかの手順を実行します。

    1. 既存のポリシーを選択し、**[編集]** を選択します。

    2. **[+ 追加]** を選択して新しいポリシーを作成します。

    > [!TIP]
    > ポリシーの作成または編集に関するヘルプについては、「[Microsoft Defender for Business でポリシーを表示または編集する](m365bp-view-edit-create-mdb-policies.md)」を参照してください。

4. **[一般情報]** ステップで 、情報を確認し、必要に応じて編集し、**[次へ]** を選択します。

5. [ **新しいグループの作成**] を選択します。

6. デバイス グループの名前と説明を指定し、**[次へ]** を選択します。

7. グループに含めるデバイスを選択し、**[グループの作成]** を選択します。

8. **[デバイス グループ]** ステップで、ポリシーのデバイス グループのリストを確認します。 必要に応じて、リストからグループを削除します。 **[次へ]** を選択します。

9. **[構成設定]** ページで、必要に応じて設定を確認および編集し、**[次へ]** を選択します。 これらの設定の詳細については、「[Microsoft Defender for Business の次世代構成設定について理解する](../security/defender-business/mdb-next-gen-configuration-settings.md)」を参照してください。

10. **[ポリシーの確認]** ステップで、すべての設定を確認し、必要な編集を行ってから、**[ポリシーの作成]** または **[ポリシーの更新]** を選択します。

## <a name="create-a-device-category-in-intune"></a>Intune でデバイス カテゴリを作成する

ユーザーがデバイスを登録するときに選択する必要があるデバイス カテゴリを Intune で作成します。

1. Microsoft エンドポイント マネージャー管理センター

2. **[デバイス]** > **[デバイス カテゴリ]** > **を選択します。デバイス カテゴリ** を作成して、新しいカテゴリを追加します。

3. [ **デバイス カテゴリの作成** ] ウィンドウで、新しいカテゴリの名前とオプションの説明を入力します。

4. 完了したら、[ **作成**] を選択します。 新しいカテゴリが一覧に表示されます。

Azure Active Directory (Azure AD) セキュリティ グループを作成するときは、デバイス カテゴリ名を使用します。 ユーザーがデバイスを登録すると、Intune で構成したカテゴリの一覧が表示されます。 ユーザーがカテゴリを選択して登録を完了すると、選択したカテゴリに対応する Active Directory セキュリティ グループにデバイスが追加されます。

## <a name="create-dynamic-device-groups-in-azure-active-directory"></a>Azure Active Directoryで動的デバイス グループを作成する

Microsoft 365 管理センターからAzure Active Directory (Azure AD) ポータル ([https://portal.azure.com](https://portal.azure.com)) を入力することもできます。 Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com/)) で、[ **すべての管理センター**] を選択し、[ **Azure Active Directory**]を選択します。

Azure AD ポータルでは、デバイス カテゴリとデバイス カテゴリ名に基づいて動的グループを作成できます。 動的グループルールを使用して、デバイスを自動的に追加および削除します。 デバイスの属性が変更された場合、システムはディレクトリの動的グループ ルールを調べて、デバイスが規則の要件を満たしているか (追加される)、または規則の要件を満たしていない (削除される) かどうかを確認します。

動的グループはデバイスまたはユーザーのいずれかに作成できますが、両方には作成できません。 デバイス所有者の属性に基づいてデバイス グループを作成することもできません。 デバイス メンバーシップルールは、デバイスの属性のみを参照できます。 

## <a name="after-device-groups-are-created"></a>デバイス グループの作成後

カテゴリとデバイス グループが確立されたので、iOS と Android デバイスのユーザーはデバイスを登録し、その際に、構成されたカテゴリの一覧からカテゴリを選択する必要があります。 Windows ユーザーは、ポータル サイト Web サイトまたはポータル サイト アプリを使用してカテゴリを選択できます。

1. デバイスを登録した後、[company portal](https://portal.microsoft.com) に移動し **My Devices** を選択します。

2. 一覧から登録済みデバイスを選択し、それからカテゴリを選択します。

カテゴリを選択すると、デバイスが対応するグループに自動的に追加されます。 カテゴリを構成する前にデバイスが既に登録されている場合、ユーザーにはポータル Web サイトのデバイスに関する通知が表示されます。 これで、ユーザーが次回 iOS/iPadOS または Android でポータル サイト アプリにアクセスするときに、カテゴリの選択について知らせることができます。

> [!NOTE]
> - Azure Portal でデバイス カテゴリを編集できますが、このカテゴリを参照するすべての Azure AD セキュリティ グループを手動で更新する必要があります。
> - カテゴリを削除すると、そのカテゴリに割り当てられていたデバイスのカテゴリ名が "**未割り当て**" と表示されます。

## <a name="view-the-categories-of-devices-that-you-manage"></a>管理対象デバイスのカテゴリを表示する

1. [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) にサインインして、**[デバイス]** > **[すべてのデバイス]** を選択します。

2. デバイスの一覧の **[デバイス カテゴリ]** 列を確認します。

3. [デバイス カテゴリ] 列が表示されていない場合は、**[列]** > **[カテゴリ]** > **[適用]** の順に選択します。

## <a name="change-the-category-of-a-device"></a>デバイスのカテゴリを変更する

1. [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) にサインインして、**[デバイス]** > **[すべてのデバイス]** を選択します。 

2. 一覧から目的のカテゴリを選択して、そのプロパティを表示します。

## <a name="next-steps"></a>次の手順

主要なミッションを完了したので、時間をかけて [対応チーム](m365bp-security-incident-management.md) を設定し、 [環境を維持します](m365bp-maintain-environment.md)。
