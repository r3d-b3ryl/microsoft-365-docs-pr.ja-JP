---
title: Microsoft Defender for Businessでロールとアクセス許可を割り当てる
description: サイバーセキュリティ チームにロールを割り当てます。 Defender for Business のこれらのロールとアクセス許可について説明します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 03295989e1ee44ab43fe0cc53e4029a6c4307ea8
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2022
ms.locfileid: "65172647"
---
# <a name="assign-roles-and-permissions-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでロールとアクセス許可を割り当てる

Microsoft Defender for Businessの構成、レポートの表示、検出された脅威に対する応答アクションの実行など、Microsoft 365 Defender ポータルでタスクを実行するには、セキュリティ チームに適切なアクセス許可を割り当てる必要があります。 アクセス許可は、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) または[Azure Active Directory](/azure/active-directory/roles/manage-roles-portal)で割り当てられているロールを通じて付与されます。 

## <a name="what-to-do"></a>操作

1. [Defender for Business のロールについて説明します](#roles-in-defender-for-business)。
2. [セキュリティ チームのロールの割り当てを表示または編集](#view-or-edit-role-assignments)します。
3. [次の手順に進みます](#next-steps)。

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">セキュリティに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="roles-in-defender-for-business"></a>Defender for Business のロール

次の表では、Defender for Business で割り当てることができる 3 つのロールについて説明します。 [管理者ロールの詳細情報](../../admin/add-users/about-admin-roles.md)。

| 権限レベル | 説明 |
|:---|:---|
| **グローバル管理者** (グローバル管理者とも呼ばれます) <br/><br/> *ベスト プラクティスとして、グローバル管理者の数を制限します。* | グローバル管理者は、あらゆる種類のタスクを実行できます。 Microsoft 365またはMicrosoft Defender for Businessに会社をサインアップしたユーザーは、既定でグローバル管理者です。 <br/><br/> グローバル管理者は、次のようなすべてのMicrosoft 365 ポータルで設定にアクセス/変更できます。 <br/>- Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com)) <br/>- Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) |
| **セキュリティ管理者** (セキュリティ管理者とも呼ばれます) | セキュリティ管理者は、次のタスクを実行できます。 <br/>- セキュリティ ポリシーの表示と管理 <br/>- セキュリティの脅威とアラートの表示と管理 (これらのアクティビティには、エンドポイントに対する応答アクションの実行が含まれます) <br/>- セキュリティ情報とレポートを表示する |
| **セキュリティ閲覧者** | セキュリティ リーダーは、次のタスクを実行できます。 <br/>- セキュリティ ポリシーを表示する <br/>- セキュリティの脅威とアラートを表示する <br/>- セキュリティ情報とレポートを表示する  |


## <a name="view-or-edit-role-assignments"></a>ロールの割り当てを表示または編集する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで[**アクセス許可&ロール**]、[**Azure AD**] の [**ロール**] の順に選択します。

3. 次のいずれかのロールを選択して、サイド ウィンドウを開きます。

   - グローバル管理者
   - セキュリティ管理者
   - セキュリティ閲覧者

   > [!IMPORTANT]
   > Microsoft では、ユーザーにタスクを実行するために必要なもののみにアクセス権を付与することをお勧めします。 この概念は、アクセス許可に対する *最小限の特権* と呼びます。 詳細については、 [アプリケーションの最小特権アクセスのベスト プラクティスに関するページを](/azure/active-directory/develop/secure-least-privileged-access)参照してください。 

4. サイド ウィンドウで、[**Azure ADのメンバーの管理**] リンクを選択します。 このアクションでは、ロールの割り当てを表示および管理できるAzure Active Directory (Azure AD) に移動します。

5. ユーザーを選択してプロファイルを開き、[ **割り当てられたロール**] を選択します。

   - ロールを追加するには、[ **+ 割り当ての追加]** を選択します。
   - ロールを削除するには、[ **X 割り当ての削除]** を選択します。 

## <a name="need-to-add-users"></a>ユーザーを追加する必要がありますか?

サブスクリプションにまだユーザーを追加していない場合は、「 [ユーザーの追加とライセンスの割り当て」を同時に](mdb-add-users.md)参照してください。

## <a name="next-steps"></a>次の手順

次の手順に進みます。

- [手順 3: 電子メール通知を設定する](mdb-email-notifications.md)
- [手順 4: デバイスをMicrosoft Defender for Businessにオンボードする](mdb-onboard-devices.md)