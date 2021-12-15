---
title: Microsoft Defender for Business でポリシーを表示または編集する (プレビュー)
description: Microsoft Defender for Business (プレビュー) で次世代の保護ポリシーを表示、編集、作成、および削除する方法について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: aed09fd10f3381b4d167ea31e303fc2cbce7e8f3
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2021
ms.locfileid: "61508337"
---
# <a name="view-or-edit-policies-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business でポリシーを表示または編集する (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft Defender for Business (プレビュー) では、セキュリティ設定はポリシーによって構成されます。 Defender for Business (プレビュー) には、主に次の 2 種類のポリシーがあります。

- **次世代の保護ポリシー 。** このポリシーは、Microsoft Defender ウイルス対策その他の脅威保護機能の構成方法を決定します。
- **ファイアウォール ポリシー :** 会社のデバイスに対して、どのネットワーク トラフィックが流れるかを決定します。

**この記事では、次の方法について説明します**。

- [既存のポリシーを表示する](#view-your-existing-policies)
- [既存のポリシーを編集する](#edit-an-existing-policy)

> [!TIP]
> 新しいポリシーを追加する場合は、「新しいポリシーを作成 [する」を参照してください](mdb-create-new-policy.md)。

## <a name="view-your-existing-policies"></a>既存のポリシーを表示する

1. ポータル ( ) にMicrosoft 365 Defender [https://security.microsoft.com](https://security.microsoft.com) し、サインインします。 

2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 ポリシーは、オペレーティング システム (Windows クライアントなど)**と** ポリシーの種類 (次世代保護やファイアウォールなど)**によって** 編成 **されます**。 

3. [オペレーティング システム] タブ (Windows クライアントなど)**を選択** し、[次世代の保護] カテゴリと [ファイアウォール] カテゴリの下のポリシーの一覧を **確認** します。 

4. ポリシーの詳細を表示するには、その名前を選択します。 サイド ウィンドウが開き、そのポリシーに関する詳細 (そのポリシーで保護されているデバイスなど) が表示されます。

## <a name="edit-an-existing-policy"></a>既存のポリシーを編集する

1. ポータル ( ) にMicrosoft 365 Defender [https://security.microsoft.com](https://security.microsoft.com) し、サインインします。 

2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 ポリシーは、オペレーティング システム (Windows クライアントなど)**と** ポリシーの種類 (次世代保護やファイアウォールなど)**によって** 編成 **されます**。 

3. [オペレーティング システム] タブ (Windows クライアントなど)**を選択** し、[次世代の保護] カテゴリと [ファイアウォール] カテゴリの下のポリシーの一覧を **確認** します。 

4. ポリシーを編集するには、ポリシーの名前を選択し、[編集] を **選択します**。

5. [全般情報 **] タブで** 、情報を確認します。 必要に応じて、説明を編集できます。 **[次へ]** を選択します。

6. [デバイス グループ **] タブで** 、このポリシーを受け取るデバイス グループを決定します。  

   - 選択したデバイス グループを保持するには、[次へ] を **選択します**。
   - ポリシーからデバイス グループを削除するには、[削除] を **選択します**。
   - 新しいデバイス グループを設定するには、[新しい **グループの作成**] を選択し、デバイス グループを設定します。 (このタスクのヘルプを表示するには [、「Microsoft Defender for Business (プレビュー) のデバイス グループ」を参照](mdb-create-edit-device-groups.md)してください。
   - ポリシーを別のデバイス グループに適用するには、[既存のグループを使用 **する] を選択します**。

   ポリシーを受信するデバイス グループを指定した後、[次へ] を **選択します**。

7. [構成設定 **] タブで** 、設定を確認します。 必要に応じて、ポリシーの設定を編集できます。 このタスクのヘルプを表示するには、次の記事を参照してください。 

   - [次世代の構成設定について](mdb-next-gen-configuration-settings.md)   
   - [ファイアウォールの設定](mdb-firewall.md)

   次世代の保護設定を指定した後、[次へ] を **選択します**。

8. [ポリシー **の確認] タブで** 、一般的な情報、対象デバイス、および構成設定を確認します。 

   - [編集] を選択して、必要な変更を **行います**。
   - 続行する準備ができたら、[ポリシーの更新] **を選択します**。


## <a name="next-steps"></a>次の手順

次のタスクの 1 つ以上を選択します。

- [デバイスの管理](mdb-manage-devices.md)

- [Microsoft Defender for Business で新しいポリシーを作成する (プレビュー)](mdb-create-new-policy.md)

- [Microsoft Defender for Business でのインシデントの表示と管理 (プレビュー)](mdb-view-manage-incidents.md)

- [Microsoft Defender for Business での脅威への対応と軽減 (プレビュー)](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)