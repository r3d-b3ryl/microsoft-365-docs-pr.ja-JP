---
title: Canvas でMicrosoft Teams会議を使用する
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: キャンバスMicrosoft Teams会議を統合する
ms.openlocfilehash: 5ba812ba2f5694dd7860131479f01fceaba9ab2a040d1ba828306aa022665f74
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53819287"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Canvas でMicrosoft Teams会議を使用する

Microsoft Teamsは、ラーニング ツール相互運用性 (LTI) アプリであり、教育者と学生が ラーニング 管理システム (LMS) と Teams の間を簡単に移動するのに役立ちます。 ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。

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

 - Microsoft Teams会議 - 170000000000703

1. Access **Admin settings**  >  **Apps**.

2. [+**アプリ] を** 選択して、LTI Teamsを追加します。

   ![外部アプリ](media/external-apps.png)

3. 構成 **の種類として [クライアント ID 別** ] を選択します。

   ![アプリの追加](media/add-app.png)

4. 指定されたクライアント ID を入力し、[送信] を **選択します**。

   確認のためにクライアント ID のMicrosoft Teams LTI アプリ名が表示されます。

5. **[インストール]** を選択します。

   会議Microsoft Teams LTI アプリが外部アプリの一覧に追加されます。
   
## <a name="enable-for-canvas-courses"></a>キャンバス コースを有効にする

コース内で LTI を使用するには、Canvas コースの講師が統合同期を有効にする必要があります。各コースは、作成する対応するTeams教員が有効にする必要があります。作成のグローバルメカニズムTeamsはありません。 これは、不要なデータが作成されるのを防ぐためにTeams設計されています。

各コースで LTI[](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas)を有効にし、統合セットアップを完了するには、教員のドキュメントを参照してください。
