---
title: Canvas でMicrosoft Teams会議を使用する
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: キャンバスMicrosoft Teams会議を統合する
ms.openlocfilehash: 8ccf1c1d45d38fa4a92b556146744a2c17cd5105
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821893"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Canvas でMicrosoft Teams会議を使用する

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft Teamsはラーニング ツール相互運用性 (LTI) アプリで、教育者と学生が学習管理システム (LMS) と学生の間を簡単に移動Teams。 ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365管理者

Instructure Canvas 内の Microsoft Teams 統合を管理する前に、Canvas の管理セットアップを完了する前に、キャンバスの **microsoft-Teams-Sync-for-Canvas** Azure アプリを Microsoft Azure テナントの教育機関の Microsoft Office 365 管理者によって承認することが重要です。

1. Canvas にサインインします。
 
2. グローバル ナビゲーション **で [管理者** ] リンクを選択し、アカウントを選択します。

3. 管理ナビゲーションで、[リンク]**リンクを** 設定、[統合]**タブを選択** します。 

4. Microsoft テナント名とログイン属性を入力します。 

   login 属性は、Canvas ユーザーをユーザーに関連付Azure Active Directoryされます。 

5. [完了 **したら設定** 更新] を選択します。

6. Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリへのアクセスを承認するには、[テナント アクセスを **許可する] リンクを選択** します。 Microsoft Identity Platform Admin Consent Endpoint にリダイレクトされます。

   ![permissions](media/permissions.png)

7. **[同意する]** を選択します。
 
8. トグルをオンにしてMicrosoft Teams同期を有効にします。

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a>Canvas Admin

LTI 1.3 Microsoft Teamsをセットアップします。

Canvas Admin として、環境内に会議 LTI Microsoft Teamsを追加する必要があります。 アプリの LTI クライアント ID をメモします。

 - Microsoft Teams会議 - 17000000000000703

1. Access **Admin settings**  >  **Apps**.

2. [+**アプリ] を** 選択して、LTI Teamsを追加します。 
 
   ![外部アプリ](media/external-apps.png)

3. 構成 **の種類として [クライアント ID 別** ] を選択します。

   ![アプリの追加](media/add-app.png)

4. 指定されたクライアント ID を入力し、[送信] を **選択します**。
   
   確認のためにクライアント ID のMicrosoft Teams LTI アプリ名が表示されます。 

5. **[インストール]** を選択します。

   会議Microsoft Teams LTI アプリが外部アプリの一覧に追加されます。
