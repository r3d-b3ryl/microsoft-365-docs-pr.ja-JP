---
title: Microsoft Defender for Business のデバイス グループ
description: Microsoft Defender for Business のデバイス グループの詳細
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: aeccd145f8bc7e5dd65ea98696fd10a63fc86def
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2021
ms.locfileid: "61508361"
---
# <a name="device-groups-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business のデバイス グループ (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business (プレビュー) では、ポリシーはデバイス グループと呼ばれる特定のコレクションを介してデバイスに適用されます。 

**この記事では、以下について説明します**。  

- [デバイス グループ](#what-is-a-device-group)   
- [Defender for Business でデバイス グループを作成する方法](#create-a-new-device-group)

## <a name="what-is-a-device-group"></a>デバイス グループとは

デバイス グループは、オペレーティング システムのバージョンなど、特定の指定された条件のためにグループ化されたデバイスのコレクションです。 条件を満たすデバイスは、除外しない限り、そのデバイス グループに含まれます。 Microsoft Defender for Business (プレビュー) では、ポリシーはデバイス グループを使用してデバイスに適用されます。 

Defender for Business (プレビュー) には、使用できる既定のデバイス グループが含まれています。 既定のデバイス グループには、Defender for Business (プレビュー) にオンボードされているすべてのデバイスが含まれます。 ただし、特定の設定を持つポリシーを特定のデバイスに割り当てる新しいデバイス グループを作成することもできます。 

既定のデバイス グループと、定義したカスタム デバイス グループを含むすべての[デバイス](/azure/active-directory/fundamentals/active-directory-whatis)グループは、Azure Active Directory (Azure AD) に保存されます。

## <a name="create-a-new-device-group"></a>新しいデバイス グループを作成する

現在、Defender for Business (プレビュー) では、次の手順で説明するように、ポリシーの作成または編集中に新しいデバイス グループを作成できます。 

1. ポータル ( ) にMicrosoft 365 Defenderサインイン [https://security.microsoft.com](https://security.microsoft.com) します。

2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 

3. 次のいずれかの操作を実行します。

    1. 既存のポリシーを選択し、[編集] を **選択します**。
    2. [+ **追加] を選択** して新しいポリシーを作成します。

    > [!TIP]
    > ポリシーの作成または編集に関するヘルプについては、「Microsoft Defender for Business でポリシーを表示または編集 [する」を参照してください](mdb-view-edit-policies.md)。

4. [全般情報 **] ステップで** 、情報を確認し、必要に応じて編集し、[次へ] を **選択します**。

5. [+ **新しいグループの作成] を選択します**。 

6. デバイス グループの名前と説明を指定し、[次へ] を **選択します**。

7. グループに含めるデバイスを選択し、[グループの作成] **を選択します**。

8. [デバイス グループ **] ステップ** で、ポリシーのデバイス グループの一覧を確認します。 必要に応じて、リストからグループを削除します。 **[次へ]** を選択します。

9. [構成設定 **] ページで** 、必要に応じて設定を確認および編集し、[次へ] を **選択します**。 これらの設定の詳細については、「構成設定」 [を参照してください](mdb-next-gen-configuration-settings.md)。

10. [ポリシー **の確認] ステップ** で、すべての設定を確認し、必要な編集を行い、[ポリシーの作成] または [ポリシーの更新]**を選択します**。

## <a name="next-steps"></a>次の手順

次のタスクの 1 つ以上を選択します。

- [ポリシーの表示または編集](mdb-view-edit-policies.md)

- [新しいポリシーの作成](mdb-create-new-policy.md)

- [Microsoft Defender for Business でのインシデントの表示と管理 (プレビュー)](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減 (プレビュー)](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)