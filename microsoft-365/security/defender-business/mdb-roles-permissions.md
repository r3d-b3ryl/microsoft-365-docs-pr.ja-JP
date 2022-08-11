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
ms.date: 08/09/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365solution-mdb-setup
ms.openlocfilehash: b8e884c207479a7d2781e1ea4e31b9ee91bd25db
ms.sourcegitcommit: 6bff75867764335685f972943170c7db46e33a6f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2022
ms.locfileid: "67300894"
---
# <a name="assign-roles-and-permissions-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでロールとアクセス許可を割り当てる

Defender for Business の構成、レポートの表示、検出された脅威に対する応答アクションの実行など、Microsoft 365 Defender ポータルでタスクを実行するには、セキュリティ チームに適切なアクセス許可を割り当てる必要があります。 アクセス許可は、Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) または [Azure Active Directory](/azure/active-directory/roles/manage-roles-portal) で割り当てられているロールを通じて付与されます。 

## <a name="what-to-do"></a>操作

1. [Defender for Business の役割について学ぶ](#roles-in-defender-for-business)。
2. [セキュリティ チームの役割の割り当てを表示または編集する](#view-or-edit-role-assignments)。
3. [次の手順に進みます](#next-steps)。


## <a name="roles-in-defender-for-business"></a>Defender for Business のロール

次の表では、Defender for Business で割り当てることができる 3 つのロールについて説明します。 [管理者ロールの詳細情報](../../admin/add-users/about-admin-roles.md)。

| 権限レベル | 説明 |
|:---|:---|
| **グローバル管理者** (グローバル管理者とも呼ばれます) <p> *ベスト プラクティスとして、グローバル管理者の数を制限します。* | グローバル管理者は、あらゆる種類のタスクを実行できます。 Microsoft 365 または Defender for Business に会社をサインアップしたユーザーは、既定でグローバル管理者です。 <p> グローバル管理者は、次のようなすべての Microsoft 365 ポータルの設定を変更できます。 <ul><li>Microsoft 365 管理センター ([https://admin.microsoft.com](https://admin.microsoft.com))</li><li>Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com))</li></ul> |
| **セキュリティ管理者** (セキュリティ管理者とも呼ばれます) | セキュリティ管理者は、次のタスクを実行できます。 <ul><li>セキュリティ ポリシーの表示と管理</li><li>セキュリティの脅威とアラートの表示と管理 (これらのアクティビティには、エンドポイントに対する応答アクションの実行が含まれます)</li><li>セキュリティ情報とレポートを表示する</li></ul> |
| **セキュリティ閲覧者** | セキュリティ リーダーは、次のタスクを実行できます。<ul><li>セキュリティ ポリシーを表示する</li><li>セキュリティの脅威とアラートを表示する</li><li>セキュリティ情報とレポートを表示する</li></ul>  |


## <a name="view-or-edit-role-assignments"></a>ロールの割り当てを表示または編集する

1. Microsoft 365 Defender ポータル ([https://security.microsoft.com](https://security.microsoft.com)) に移動してサインインします。

2. ナビゲーション ウィンドウで[ **アクセス許可&ロール**]、[ **Azure AD**] の [ **ロール**] の順に選択します。

3. 次のいずれかのロールを選択して、サイド ウィンドウを開きます。

   - グローバル管理者
   - セキュリティ管理者
   - セキュリティ閲覧者

   > [!IMPORTANT]
   > Microsoft では、ユーザーにタスクを実行するために必要なもののみにアクセス権を付与することをお勧めします。 この概念は、アクセス許可に対する *最小限の特権* と呼びます。 詳細については、 [アプリケーションの最小特権アクセスのベスト プラクティスに関するページを](/azure/active-directory/develop/secure-least-privileged-access)参照してください。 

4. サイド ウィンドウで、[ **Azure AD のメンバーの管理** ] リンクを選択します。 このアクションを実行すると、Azure Active Directory (Azure AD) に移動し、ロールの割り当てを表示および管理できます。

5. ユーザーを選択してプロファイルを開き、[ **割り当てられたロール**] を選択します。

   - ロールを追加するには、[ **+ 割り当ての追加]** を選択します。
   - ロールを削除するには、[ **X 割り当ての削除]** を選択します。 

## <a name="need-to-add-users"></a>ユーザーを追加する必要がありますか?

サブスクリプションにまだユーザーを追加していない場合は、「 [ユーザーの追加とライセンスの割り当て」を同時に](mdb-add-users.md)参照してください。

## <a name="next-steps"></a>次の手順

行きます：

- [手順 3: 電子メール通知を設定する](mdb-email-notifications.md)
- [手順 4: Defender for Business にデバイスをオンボードする](mdb-onboard-devices.md)