---
title: Microsoft Defender for Business で新しいポリシーを作成する
description: Microsoft Defender for Business で新しいセキュリティ ポリシーを作成する方法について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: caa6013a68ab8ed50b16d26dcc24e91ac7d55616
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61375433"
---
# <a name="create-a-new-policy-in-microsoft-defender-for-business"></a>Microsoft Defender for Business で新しいポリシーを作成する

> [!IMPORTANT]
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 この記事には、Microsoft Defender for Business (プレビュー) に含まれていない一部の機能について説明する可能性があるオンライン コンテンツへのリンクが含まれています。

Microsoft Defender for Business には、会社のデバイスを 1 日目から保護するために推奨設定を使用する既定のポリシーが含まれています。 たとえば、推奨されるセキュリティ **設定を** 使用して組み込みの次世代保護ポリシーとファイアウォール ポリシーがあります。 ただし、既定のポリシーに限定されません。 この記事で説明するように、新しいポリシーも作成できます。

> [!TIP]
> 既存のポリシーを編集する場合は、「Microsoft Defender for Business でポリシーを表示または編集する [」を参照してください](mdb-view-edit-policies.md)。

## <a name="create-a-new-policy"></a>新しいポリシーの作成

1. ポータル ( ) にMicrosoft 365 Defender [https://security.microsoft.com](https://security.microsoft.com) し、サインインします。 

2. ナビゲーション ウィンドウで、[デバイス構成] **を選択します**。 ポリシーは、オペレーティング システム (Windows クライアントなど)**と** ポリシーの種類 (次世代保護やファイアウォールなど)**によって** 編成 **されます**。 

3. [オペレーティング システム] タブ (たとえば **、Windows) を** 選択し、次に、次世代保護ポリシーの一 **覧を** 確認します。 

4. [ **次世代の保護] または [ファイアウォール]** **で、[+** 追加 **] を選択します**。

5. [全般情報 **] タブ** で、次の手順を実行します。

   1. 名前と説明を指定します。 この情報は、後でユーザーとチームがポリシーを識別するのに役立ちます。
   2. ポリシーの順序を確認し、必要に応じて編集します。 (詳細については、「Policy order .」 [を参照](mdb-policy-order.md)してください。
   3. **次へ** を選択します。 

7. [デバイス グループ **] タブ** で、新しいデバイス グループを作成するか、既存のグループを使用します。 ポリシーは、デバイス グループを介してデバイスに割り当てられます。 以下に注意する必要があるものがあります。

   - 最初は、会社のユーザーが会社のデータと電子メールにアクセスするために使用しているデバイスを含む、既定のデバイス グループのみを持っている可能性があります。 既定のデバイス グループを保持して使用できます。
   - 既定のポリシーとは異なる特定の設定を持つポリシーを適用する新しいデバイス グループを作成します。 
   - デバイス グループを設定するときに、オペレーティング システムのバージョンなど、特定の条件を指定します。 条件を満たすデバイスは、除外しない限り、そのデバイス グループに含まれます。 
   - 定義する既定のデバイス グループとカスタム デバイス グループを含むすべてのデバイス グループは、Azure Active Directory (Azure AD) に格納されます。

   デバイス グループの詳細については、「. 

8. [構成 **設定] タブ** で、ポリシーの設定を指定し、[次へ] を **選択します**。 個々の設定の詳細については [、「Microsoft Defender for Business の構成設定」を参照してください](mdb-next-gen-configuration-settings.md)。

9. [ポリシー **の確認] タブで** 、一般的な情報、対象デバイス、および構成設定を確認します。 

   - [編集] を選択して、必要な変更を **行います**。
   - 続行する準備ができたら、[ポリシーの作成] **を選択します**。

## <a name="next-steps"></a>次の手順

次のタスクの 1 つ以上を選択します。

- [Defender for Business の使用を開始する](mdb-get-started.md)

- [ポリシーの表示または編集](mdb-view-edit-policies.md)

- [デバイスの管理](mdb-manage-devices.md)

- [インシデントの表示と管理](mdb-view-manage-incidents.md)

- [脅威への対応と軽減](mdb-respond-mitigate-threats.md)

- [アクション センターで修復アクションを確認する](mdb-review-remediation-actions.md)