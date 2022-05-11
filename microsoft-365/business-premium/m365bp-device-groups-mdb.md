---
title: Microsoft 365 Business Premium でのデバイス グループの操作
description: Microsoft 365 Business Premium のデバイス グループについて説明します
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 03/16/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: high
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 2c218cd2b0f04201f46155a72a916cc7676aaddb
ms.sourcegitcommit: 7dc7e9fd76adf848f941919f86ca25eecc704015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2022
ms.locfileid: "65320820"
---
# <a name="device-groups-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premium のデバイス グループ

Microsoft 365 Business Premium には、Microsoft Defender for Business によるエンドポイント保護が含まれます。 デバイス保護ポリシーは、デバイス グループと呼ばれる特定のコレクションを通じてデバイスに適用されます。 

**このガイダンスでは、次について説明します**。  

- [デバイス グループとは](#whats-a-device-group)
- [新しいデバイス グループを作成する方法](#how-do-i-create-a-new-device-group)

## <a name="whats-a-device-group"></a>デバイス グループとは何ですか?

デバイス グループは、オペレーティング システムのバージョンなど、特定の指定された条件のためにグループ化されたデバイスのコレクションです。 条件を満たすデバイスは、除外しない限り、そのデバイス グループに含まれます。 

サブスクリプションには、使用できる既定のデバイス グループがあります。 既定のデバイス グループには、Defender for Business にオンボードされているすべてのデバイスが含まれます。 ただし、特定のデバイスに特定の設定を持つデバイス保護ポリシーを割り当てるために、新しいデバイス グループを作成することもできます。 

既定のデバイス グループと定義したカスタム デバイス グループを含むすべてのデバイス グループは、[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis) (Azure AD) に格納されます。

## <a name="how-do-i-create-a-new-device-group"></a>新しいルールを作成する方法

デバイス保護ポリシーの作成中または編集中に、新しいデバイス グループを作成できます。 

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。 

3. 次のどちらかの手順を実行します。

    1. 既存のポリシーを選択し、**[編集]** を選択します。
    
    2. **[+ 追加]** を選択して新しいポリシーを作成します。

    > [!TIP]
    > ポリシーの作成または編集に関するヘルプについては、「[Microsoft Defender for Business でポリシーを表示または編集する](m365bp-view-edit-create-mdb-policies.md)」を参照してください。

4. **[一般情報]** ステップで 、情報を確認し、必要に応じて編集し、**[次へ]** を選択します。

5. **[+ 新しいグループの作成]** を選択します。 

6. デバイス グループの名前と説明を指定し、**[次へ]** を選択します。

7. グループに含めるデバイスを選択し、**[グループの作成]** を選択します。

8. **[デバイス グループ]** ステップで、ポリシーのデバイス グループのリストを確認します。 必要に応じて、リストからグループを削除します。 **[次へ]** を選択します。

9. **[構成設定]** ページで、必要に応じて設定を確認および編集し、**[次へ]** を選択します。 これらの設定の詳細については、「[Microsoft Defender for Business の次世代構成設定について理解する](../security/defender-business/mdb-next-gen-configuration-settings.md)」を参照してください。

10. **[ポリシーの確認]** ステップで、すべての設定を確認し、必要な編集を行ってから、**[ポリシーの作成]** または **[ポリシーの更新]** を選択します。

## <a name="next-steps"></a>次の手順

これで主要なミッションが完了したので、[応答チーム](m365bp-security-incident-management.md)を設定し、[環境を維持します](m365bp-maintain-environment.md)。

