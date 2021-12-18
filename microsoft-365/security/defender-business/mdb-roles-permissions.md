---
title: Microsoft Defender for Business での役割とアクセス許可の割り当て (プレビュー)
description: Microsoft Defender for Business (プレビュー) で役割とアクセス許可を割り当てる方法について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/13/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 1a003bc5ad0208972f03e761dbfb251c2b2509b0
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2021
ms.locfileid: "61507424"
---
# <a name="assign-roles-and-permissions-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business での役割とアクセス許可の割り当て (プレビュー)

> [!IMPORTANT]
> Microsoft Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と[](https://aka.ms/mdb-preview)IT パートナーに徐々にロールアウトされます。 今後数週間以内に最初の一連の顧客とパートナーをオンボードし、一般提供に至るプレビューを拡大します。 プレビューは一連のシナリオで [起動](mdb-tutorials.md#try-these-preview-scenarios)し、定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

microsoft Defender for Business (プレビュー) の構成、レポートの表示、検出された脅威に対する対応アクションの実行など、Microsoft 365 Defender ポータルでタスクを実行するには、セキュリティ チームに適切なアクセス許可を割り当てる必要があります。 アクセス許可は、ポータル ( ) または Microsoft 365 Defenderで割り当てられている役割 [https://security.microsoft.com](https://security.microsoft.com) を[通じて付与Azure Active Directory。](/azure/active-directory/roles/manage-roles-portal) 

## <a name="what-to-do"></a>操作

1. [Defender for Business (プレビュー) の役割について学習します](#roles-in-defender-for-business)。

2. [セキュリティ チームの役割の割り当てを表示または編集します](#view-or-edit-role-assignments)。

3. [次の手順に進みます](#next-steps)。

## <a name="roles-in-defender-for-business"></a>ビジネス向け Defender の役割

次の表に、Defender for Business (プレビュー) で割り当て可能な 3 つの役割について説明します。 [管理者ロールの詳細情報](../../admin/add-users/about-admin-roles.md)。 <br/><br/>

| 権限レベル | 説明 |
|:---|:---|
| **グローバル管理者** (グローバル管理者とも呼ばれます) <br/><br/> *ベスト プラクティスとして、グローバル管理者の数を制限します。* | グローバル管理者は、あらゆる種類のタスクを実行できます。 既定では、Microsoft Defender for Business (プレビュー) Microsoft 365または Microsoft Defender の会社にサインアップしたユーザーは、グローバル管理者です。 <br/><br/> グローバル管理者は、次のようなすべてのポータルMicrosoft 365設定にアクセス/変更できます。 <br/>- Microsoft 365 管理センター ( [https://admin.microsoft.com](https://admin.microsoft.com) ) <br/>- Microsoft 365 Defender ポータル ( [https://security.microsoft.com](https://security.microsoft.com) ) |
| **セキュリティ管理者** (セキュリティ管理者とも呼ばれます) | セキュリティ管理者は、次のタスクを実行できます。 <br/>- セキュリティ ポリシーと設定の表示と管理 <br/>- セキュリティの脅威とアラートの表示と管理 (これらのアクティビティには、エンドポイントでの応答アクションの実行が含まれます) <br/>- セキュリティ情報とレポートの表示 |
| **セキュリティ閲覧者** | セキュリティ リーダーは、次のタスクを実行できます。 <br/>- セキュリティ ポリシーと設定の表示 <br/>- セキュリティの脅威とアラートを表示する <br/>- セキュリティ情報とレポートの表示  |


## <a name="view-or-edit-role-assignments"></a>役割の割り当てを表示または編集する

1. ポータル ( ) にMicrosoft 365 Defenderサインイン [https://security.microsoft.com](https://security.microsoft.com) します。

2. ナビゲーション ウィンドウで、[アクセス許可] を選択&**し**、[アクセス許可] の下にある [Azure AD]**を****選択します**。

3. 次のいずれかの役割を選択して、サイド ウィンドウを開きます。

   - グローバル管理者
   - セキュリティ管理者
   - セキュリティ閲覧者

   > [!IMPORTANT]
   > Microsoft では、タスクを実行するために必要なアクセスのみをユーザーに付与する方法をお勧めします。 この概念は、アクセス *許可の最小特権* と呼ばれる。 詳細については、「アプリケーションの [最小特権アクセス](/azure/active-directory/develop/secure-least-privileged-access)のベスト プラクティス」を参照してください。 

4. サイド ウィンドウで、[メンバーの管理]**リンクをAzure AD** します。 このアクションを実行すると、Azure Active Directory (Azure AD) にアクセスして、役割の割り当てを表示および管理できます。

5. プロファイルを開くユーザーを選択し、[割り当てられた役割] **を選択します**。

   - 役割を追加するには、[+ 割り当 **ての追加] を選択します**。
   - 役割を削除するには、[X 削除] の **割り当てを選択します**。 

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 3: 電子メール通知を設定する](mdb-email-notifications.md)

- [手順 4: Microsoft Defender for Business にデバイスをオンボードする (プレビュー)](mdb-onboard-devices.md)