---
title: Microsoft Defender for Businessのデバイス グループ
description: セキュリティ ポリシーは、Defender for Business のデバイス グループを介してデバイスに適用されます。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 9d788ee4dac2e922898204fdd13e977c50e66b2e
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66090434"
---
# <a name="device-groups-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessのデバイス グループ

Microsoft Defender for Businessでは、デバイス グループと呼ばれる特定のコレクションを通じてデバイスにポリシーが適用されます。 

**この記事では、以下について説明します。**  

- [デバイス グループとは](#what-is-a-device-group)   
- [Defender for Business でデバイス グループを作成する方法](#create-a-new-device-group)
- [既存のデバイス グループを表示する方法](#view-an-existing-device-group)
- [[すべてのデバイスの追加] オプションの機能](#what-does-the-add-all-devices-option-do)


## <a name="what-is-a-device-group"></a>デバイス グループとは

デバイス グループは、オペレーティング システムのバージョンなど、特定の指定された条件のためにグループ化されたデバイスのコレクションです。 条件を満たすデバイスは、除外しない限り、そのデバイス グループに含まれます。 Microsoft Defender for Businessでは、デバイス グループを使用してデバイスにポリシーが適用されます。

Defender for Business には、使用できる既定のデバイス グループが含まれています。 既定のデバイス グループには、Defender for Business にオンボードされているすべてのデバイスが含まれます。 たとえば、Windows デバイスには既定のデバイス グループがあります。 Windowsデバイスをオンボードするたびに、デバイスは既定のデバイス グループに自動的に追加されます。

特定のデバイスに特定の設定を持つポリシーを割り当てるために、新しいデバイス グループを作成することもできます。 たとえば、ファイアウォール ポリシーを 1 つのWindows デバイスセットに割り当て、別のファイアウォール ポリシーを別のWindows デバイスのセットに割り当てるとします。 ポリシーで使用する特定のデバイス グループを定義できます。

> [!NOTE]
> Defender for Business でポリシーを作成すると、優先順位が割り当てられます。 特定のデバイス セットに複数のポリシーを適用した場合、それらのデバイスは最初に適用されたポリシーのみを受け取ります。 詳細については、「[Microsoft Defender for Businessでのポリシーの順序について](mdb-policy-order.md)理解する」を参照してください。

既定のデバイス グループと定義したカスタム デバイス グループを含むすべてのデバイス グループは、[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis) (Azure AD) に格納されます。

## <a name="create-a-new-device-group"></a>新しいデバイス グループを作成する

現在、Defender for Business では、次の手順で説明するように、ポリシーの作成または編集中に新しいデバイス グループを作成できます。 

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。 

3. 次のどちらかの手順を実行します。

    1. 既存のポリシーを選択し、**[編集]** を選択します。
    2. **[+ 追加]** を選択して新しいポリシーを作成します。

    > [!TIP]
    > ポリシーの作成または編集に関するヘルプについては、「[Microsoft Defender for Business でポリシーを表示または編集する](mdb-view-edit-policies.md)」を参照してください。

4. **[一般情報]** ステップで 、情報を確認し、必要に応じて編集し、**[次へ]** を選択します。

5. **[+ 新しいグループの作成]** を選択します。 

6. デバイス グループの名前と説明を指定し、**[次へ]** を選択します。

7. グループに含めるデバイスを選択し、**[グループの作成]** を選択します。

8. **[デバイス グループ]** ステップで、ポリシーのデバイス グループのリストを確認します。 必要に応じて、リストからグループを削除します。 **[次へ]** を選択します。

9. **[構成設定]** ページで、必要に応じて設定を確認および編集し、**[次へ]** を選択します。 これらの設定の詳細については、「 [構成設定」を](mdb-next-gen-configuration-settings.md)参照してください。

10. **[ポリシーの確認]** ステップで、すべての設定を確認し、必要な編集を行ってから、**[ポリシーの作成]** または **[ポリシーの更新]** を選択します。

## <a name="view-an-existing-device-group"></a>既存のデバイス グループを表示する

現在、Defender for Business では、次の手順で説明するように、ポリシーの作成または編集中に既存のデバイス グループを表示できます。 

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、**[デバイスの構成]** を選択します。 

3. 次のどちらかの手順を実行します。

    1. 既存のポリシーを選択し、**[編集]** を選択します。
    2. **[+ 追加]** を選択して新しいポリシーを作成します。

    > [!TIP]
    > ポリシーの作成または編集に関するヘルプについては、「[Microsoft Defender for Business でポリシーを表示または編集する](mdb-view-edit-policies.md)」を参照してください。

4. **[一般情報]** ステップで 、情報を確認し、必要に応じて編集し、**[次へ]** を選択します。

5. [ **既存のグループを使用する**] を選択します。 ポップアップが開き、デバイス グループが表示されます。 デバイス グループがまだない場合は、新しいデバイス グループの作成を求めるメッセージが表示されます。

## <a name="what-does-the-add-all-devices-option-do"></a>[すべてのデバイスの追加] オプションは何をしますか?

ポリシーを作成または編集するときに、[ **すべてのデバイスの追加]** オプションが表示される場合があります。

:::image type="content" source="media/add-all-devices-option.png" alt-text="[すべてのデバイスの追加] オプションのスクリーンショット。":::

このオプションを選択すると、Microsoft Intuneに登録されているすべてのデバイスは、既定で作成または編集しているポリシーを受け取ります。 

## <a name="next-steps"></a>次の手順

次のタスクのうち 1 つ以上を選択します。

- [ポリシーを表示または編集する](mdb-view-edit-policies.md)
- [新しいポリシーの作成](mdb-create-new-policy.md)
- [Microsoft Defender for Businessでのインシデントの表示と管理](mdb-view-manage-incidents.md)
- [Microsoft Defender for Businessの脅威に対応し、軽減する](mdb-respond-mitigate-threats.md)
- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)