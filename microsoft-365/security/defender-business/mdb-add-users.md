---
title: Microsoft Defender for Businessでユーザーを追加し、ライセンスを割り当てる
description: ユーザーを追加し、Defender for Business ライセンスを割り当ててデバイスを保護する
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.collection: M365-security-compliance
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.openlocfilehash: 7d1715352ab1a1392b06cae5bfc3ee81196bf3e2
ms.sourcegitcommit: fa90763559239c4c46c5e848939126763879d8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2022
ms.locfileid: "66994617"
---
# <a name="add-users-and-assign-licenses-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでユーザーを追加し、ライセンスを割り当てる

Defender for Business にサインアップするとすぐに、最初の手順としてユーザーを追加し、ライセンスを割り当てます。 この記事では、ユーザーを追加する方法について説明し、次の手順を含めます。

## <a name="add-users-and-assign-licenses"></a>ユーザーを追加してライセンスを割り当てる

> [!IMPORTANT]
> このタスクを実行するには、グローバル管理者である必要があります。  Microsoft 365 または Defender for Business に会社をサインアップしたユーザーは、既定でグローバル管理者です。

1. Microsoft 365 管理センターに[https://admin.microsoft.com](https://admin.microsoft.com)移動してサインインします。

2. **[ユーザーアクティブ ユーザー]** >  に移動し、[**ユーザーの追加]** を選択します。

3. [**基本設定**] ウィンドウにユーザーの基本情報を入力し、[**次へ**] を選択します。

   - **名前**: 名と姓、表示名、ユーザー名を入力します。
   - [**ドメイン**] ユーザーのアカウントのドメインを選びます。 たとえば、ユーザーのユーザー名がドメインである場合、`Pat`ユーザーは `contoso.com``pat@contoso.com`.
   - **パスワード設定**: 自動生成されたパスワードを使用するか、ユーザーに対して独自の強力なパスワードを作成するかを選択します。 ユーザーは 90 日後にパスワードを変更する必要があります。 または、[ **このユーザーが最初にサインインしたときにパスワードを変更するように要求する**] オプションを選択することもできます。 ユーザーが追加されたときに、ユーザーのパスワードを電子メールで送信するかどうかを選択することもできます。

4. [**製品ライセンスの割り当て**] ページで、Defender for Business (または Microsoft 365 Business Premium) を選択します。 **[次へ]** を選択します。 

   利用可能なライセンスがない場合でも、ユーザーを追加し、追加のライセンスを購入できます。 ユーザーの追加の詳細については、「 [ユーザーの追加とライセンスの同時割り当て](../../admin/add-users/add-users.md)」を参照してください。

5. **[オプション設定]** ページでは、[**プロファイル情報]** を展開し、ユーザーの jo タイトル、部署、場所などの詳細を入力できます。 **[次へ]** を選択します。

6. [ **校閲と終了** ] ページで詳細を確認し、[ **追加の完了]** を選択してユーザーを追加します。 変更する必要がある場合は、[ **戻る** ] を選択して前のページに戻ります。

## <a name="next-steps"></a>次の手順

- [Microsoft 365 Defender ポータルにアクセスする](mdb-get-started.md)
- [Defender for Business でセットアップ ウィザードを使用します](mdb-use-wizard.md)。