---
title: ロールとアクセス許可を割り当Microsoft Defender for Business
description: ロールとアクセス許可を割り当てる方法については、Microsoft Defender for Business
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/01/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 33fb7548d2dbd231368a459cd58b9d50e7c4673e
ms.sourcegitcommit: 7aa2441c1f2cc5b4b5495d6fdb993e563f86647f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64638248"
---
# <a name="assign-roles-and-permissions-in-microsoft-defender-for-business"></a>ロールとアクセス許可を割り当Microsoft Defender for Business

> [!IMPORTANT]
> Microsoft Defender for Business 2022 年 3 月 1 [日](../../business-premium/index.md)からMicrosoft 365 Business Premium顧客に展開しています。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー中で、ここでサインアップして要求する顧客と IT パートナーに徐 [々にロールアウト](https://aka.ms/mdb-preview) されます。 プレビューには最初 [の一連のシナリオが含まれています](mdb-tutorials.md#try-these-preview-scenarios)。定期的に機能を追加します。
> 
> この記事の一部の情報は、製品リリース前に大幅に変更される可能性がある、事前リリース済みの製品/サービスに関連しています。 Microsoft は、ここに提供される情報について、明示または黙示を問わず一切の保証を行いません。 

Microsoft 365 Defender ポータルでタスクを実行するには、Microsoft Defender for Business の構成、レポートの表示、検出された脅威に対する対応アクションの実行など、セキュリティ チームに適切なアクセス許可を割り当てる必要があります。 アクセス許可は、管理者ポータル ([https://security.microsoft.com](https://security.microsoft.com)) または Microsoft 365 Defenderで割り当てられた役割[をAzure Active Directory](/azure/active-directory/roles/manage-roles-portal)。 

## <a name="what-to-do"></a>操作

1. [Defender for Business の役割について学習します](#roles-in-defender-for-business)。

2. [セキュリティ チームの役割の割り当てを表示または編集します](#view-or-edit-role-assignments)。

3. [次の手順に進みます](#next-steps)。

>
> **少し時間ありますか?**
> お問い合<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">わせに関する短いMicrosoft Defender for Business</a>。 ご意見をお寄せください。
>

## <a name="roles-in-defender-for-business"></a>ビジネス向け Defender の役割

次の表では、Defender for Business で割り当て可能な 3 つの役割について説明します。 [管理者ロールの詳細情報](../../admin/add-users/about-admin-roles.md)。 <br/><br/>

| 権限レベル | 説明 |
|:---|:---|
| **グローバル管理者** (グローバル管理者とも呼ばれます) <br/><br/> *ベスト プラクティスとして、グローバル管理者の数を制限します。* | グローバル管理者は、あらゆる種類のタスクを実行できます。 既定では、会社に会社をMicrosoft 365またはMicrosoft Defender for Businessグローバル管理者です。 <br/><br/> グローバル管理者は、次のようなすべてのポータルMicrosoft 365設定にアクセス/変更できます。 <br/>- Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) <br/>- Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) |
| **セキュリティ管理者** (セキュリティ管理者とも呼ばれます) | セキュリティ管理者は、次のタスクを実行できます。 <br/>- セキュリティ ポリシーの表示と管理 <br/>- セキュリティの脅威とアラートの表示と管理 (これらのアクティビティには、エンドポイントでの応答アクションの実行が含まれます) <br/>- セキュリティ情報とレポートの表示 |
| **セキュリティ閲覧者** | セキュリティ リーダーは、次のタスクを実行できます。 <br/>- セキュリティ ポリシーの表示 <br/>- セキュリティの脅威とアラートを表示する <br/>- セキュリティ情報とレポートの表示  |


## <a name="view-or-edit-role-assignments"></a>役割の割り当てを表示または編集する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで、[アクセス許可] を選択&**し**、[アクセス許可] **Azure AD[役割**] を **選択します**。

3. 次のいずれかの役割を選択して、サイド ウィンドウを開きます。

   - グローバル管理者
   - セキュリティ管理者
   - セキュリティ閲覧者

   > [!IMPORTANT]
   > Microsoft では、タスクを実行するために必要なアクセスのみをユーザーに付与する方法をお勧めします。 この概念は、アクセス *許可の最小特権* と呼ばれる。 詳細については、「アプリケーションの [最小特権アクセスのベスト プラクティス」を参照してください](/azure/active-directory/develop/secure-least-privileged-access)。 

4. サイド ウィンドウで、[メンバーの管理] **リンクをAzure AD** します。 このアクションを実行すると、Azure Active Directory (Azure AD) にアクセスして、役割の割り当てを表示および管理できます。

5. プロファイルを開くユーザーを選択し、[割り当てられた役割] **を選択します**。

   - 役割を追加するには、[+ 割り当 **ての追加] を選択します**。
   - 役割を削除するには、[割り当 **ての削除] を選択します**。 

## <a name="need-to-add-users"></a>ユーザーを追加する必要がありますか?

サブスクリプションにまだユーザーを追加していない場合は、「ユーザーの追加とライセンスの同時割り当て」 [を参照してください](../../admin/add-users/add-users.md)。

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 3: 電子メール通知を設定する](mdb-email-notifications.md)

- [手順 4: デバイスをオンボードしてMicrosoft Defender for Business](mdb-onboard-devices.md)