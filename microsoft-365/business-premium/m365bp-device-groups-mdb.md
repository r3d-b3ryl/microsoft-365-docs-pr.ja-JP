---
title: デバイス グループの操作Microsoft 365 Business Premium
description: デバイス グループの詳細については、Microsoft 365 Business Premium
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 03/08/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 2cc874580dad24e1b3d5349d6075956a9e518704
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634649"
---
# <a name="device-groups-in-microsoft-365-business-premium"></a>デバイス グループ (Microsoft 365 Business Premium

Microsoft 365 Business Premiumには、エンドポイントによる保護が含Microsoft Defender for Business。 デバイス保護ポリシーは、デバイス グループと呼ばれる特定のコレクションを介してデバイスに適用されます。 

**この記事では、次の情報について説明します**。  

- [デバイス グループ](#whats-a-device-group)
- [新しいデバイス グループを作成する方法](#how-do-i-create-a-new-device-group)

## <a name="whats-a-device-group"></a>デバイス グループとは

デバイス グループは、オペレーティング システムのバージョンなど、特定の指定された条件のためにグループ化されたデバイスのコレクションです。 条件を満たすデバイスは、除外しない限り、そのデバイス グループに含まれます。 

サブスクリプションでは、使用できる既定のデバイス グループがあります。 既定のデバイス グループには、Defender for Business にオンボードされているすべてのデバイスが含まれます。 ただし、特定の設定を持つデバイス保護ポリシーを特定のデバイスに割り当てる新しいデバイス グループを作成することもできます。 

既定のデバイス グループと、ユーザーが定義したカスタム デバイス グループを含むすべてのデバイス グループは、[Azure Active Directory (Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)) に保存されます。

## <a name="how-do-i-create-a-new-device-group"></a>操作方法デバイス グループを作成しますか?

デバイス保護ポリシーの作成または編集中に、新しいデバイス グループを作成できます。 

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 

3. 次のいずれかの操作を実行します。

    1. 既存のポリシーを選択し、[編集] を **選択します**。
    
    2. [ **+ 追加] を選択** して新しいポリシーを作成します。

    > [!TIP]
    > ポリシーの作成または編集に関するヘルプについては、「ポリシーを表示[または](m365bp-view-edit-create-mdb-policies.md)編集する」を参照Microsoft Defender for Business。

4. [全般情報 **] ステップ** で、情報を確認し、必要に応じて編集し、[次へ] を選択 **します**。

5. [ **+ 新しいグループの作成] を選択します**。 

6. デバイス グループの名前と説明を指定し、[次へ] を選択 **します**。

7. グループに含めるデバイスを選択し、[グループの作成] **を選択します**。

8. [デバイス グループ **] ステップ** で、ポリシーのデバイス グループの一覧を確認します。 必要に応じて、リストからグループを削除します。 **[次へ]** を選択します。

9. [構成設定 **] ページで** 、必要に応じて設定を確認および編集し、[次へ] を選択 **します**。 これらの設定の詳細については、「[次世代](../security/defender-business/mdb-next-gen-configuration-settings.md)の構成設定について」を参照Microsoft Defender for Business。

10. [ポリシー **の確認] ステップ** で、すべての設定を確認し、必要な編集を行い、[ポリシーの作成] または [ポリシーの更新] **を選択します**。


