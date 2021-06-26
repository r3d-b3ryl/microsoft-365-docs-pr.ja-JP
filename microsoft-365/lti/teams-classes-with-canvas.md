---
title: Canvas でMicrosoft Teamsクラスを使用する
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
description: キャンバスMicrosoft Teamsクラスを統合する
ms.openlocfilehash: 8e28cc8401dbf37d6e780b8f56dc300982abd0cc
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137681"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Canvas でMicrosoft Teamsクラスを使用する

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

Microsoft Teamsクラスは、ラーニング ツール相互運用性 (LTI) アプリで、教育者と学生が ラーニング 管理システム (LMS) と Teams の間を簡単に移動するのに役立ちます。 ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365管理者

Instructure Canvas 内の Microsoft Teams 統合を管理する前に、Canvas の管理セットアップを完了する前に、キャンバスの **microsoft-Teams-Sync-for-Canvas** Azure アプリを Microsoft Azure テナントの教育機関の Microsoft Office 365 管理者によって承認することが重要です。

1. Canvas にサインインします。
 
2. グローバル ナビゲーション **で [管理者** ] リンクを選択し、アカウントを選択します。

3. 管理ナビゲーションで、[リンク]**リンクを** 設定、[統合]**タブを選択** します。 

4. トグルMicrosoft Teamsして同期を有効にします。

   ![teams-sync](media/teams-sync.png)

5. Microsoft テナント名とログイン属性を入力します。 

   login 属性は、Canvas ユーザーをユーザーに関連付Azure Active Directoryされます。 

6. [完了 **したら設定** 更新] を選択します。

7. Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリへのアクセスを承認するには、[テナント アクセスを **許可する] リンクを選択** します。 Microsoft Identity Platform Admin Consent Endpoint にリダイレクトされます。

   ![permissions](media/permissions.png)

8. **[同意する]** を選択します。
 
## <a name="canvas-admin"></a>Canvas Admin

LTI 1.3 Microsoft Teamsをセットアップします。

Canvas 管理者として、環境内に LTI Microsoft Teamsクラスを追加する必要があります。 アプリの LTI クライアント ID をメモします。

 - Microsoft Teamsクラス - 17000000000000570

1. Access **Admin settings**  >  **Apps**.

2. [+**アプリ] を** 選択して、LTI Teamsを追加します。 
 
   ![外部アプリ](media/external-apps.png)

3. 構成 **の種類として [クライアント ID 別** ] を選択します。

   ![アプリの追加](media/add-app.png)

4. 指定されたクライアント ID を入力し、[送信] を **選択します**。
   
   確認のためにクライアント ID Microsoft Teamsクラス LTI アプリ名が表示されます。 

5. **[インストール]** を選択します。

   LTI Microsoft Teamsクラスは、外部アプリの一覧に追加されます。
