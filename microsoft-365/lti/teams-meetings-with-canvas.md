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
ms.openlocfilehash: dfa9bf10400900f879c806d6ea44bdb9b4b67a9c
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58574654"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Canvas でMicrosoft Teams会議を使用する

Microsoft Teamsは、ラーニング ツール相互運用性 (LTI) アプリであり、教育者と学生が ラーニング 管理システム (LMS) と Teams の間を簡単に移動するのに役立ちます。 ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。

## <a name="prerequisites-before-deployment"></a>展開前の前提条件

> [!NOTE]
> 現在の会議Teams LTI では、キャンバス ユーザーと制限されたスコープMicrosoft Azure Active Directory (AAD) の同期のみをサポートしています。 
> - テナントに Microsoft Education ライセンスが必要です。
> - Canvas と Microsoft の間でユーザーをマッピングするには、1 つの Microsoft テナントのみを使用できます。
> - グループの重複を回避するには、学校データ同期 LTI を使用する前に、Teams (SDS) をオフにする必要があります。

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365管理者

Instructure Canvas 内の Microsoft Teams 統合を管理する前に、Canvas の管理セットアップを完了する前に、キャンバスの **microsoft-Teams-Sync-for-Canvas** Azure アプリを Microsoft Azure テナントの教育機関の Microsoft Office 365 管理者によって承認することが重要です。

1. Canvas にサインインします。

2. グローバル ナビゲーション **で [管理者** ] リンクを選択し、アカウントを選択します。

3. 管理ナビゲーションで、[リンク]**リンクを** 設定、[統合]**タブを選択** します。

![Canvas Teams更新された png を同期します。](https://user-images.githubusercontent.com/87142492/128552407-78cb28e9-47cf-4026-954d-12dc3553af6f.png)

4. Microsoft テナント名、login 属性、ドメイン サフィックス、および AAD 参照属性を入力します。 これらのフィールドは、キャンバス内のユーザーとユーザーの照合に使用Microsoft Azure Active Directory。 
   * Login Attribute は、照合に使用される Canvas ユーザー属性です。
   * サフィックス フィールドは省略可能で、Canvas 属性と Microsoft AAD フィールドの間に正確なマッピングが設定されていない場合にドメインを指定できます。 たとえば、Microsoft AAD の UPN が 'name' の場合、Canvas メールが 'name@example.edu' の場合は、接尾辞フィールドに 「example.edu」 と入力してユーザーを一致できます。
   * Active Directory Lookup Attribute は、Canvas 属性が一致する Microsoft 側のフィールドです。 UPN、プライマリ メール アドレス、または電子メール エイリアスの間で選択します。

5. [完了 **したら設定** 更新] を選択します。

6. Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリへのアクセスを承認するには、[テナント アクセスを **許可する] リンクを選択** します。 Microsoft Identity Platform Admin Consent Endpoint にリダイレクトされます。

   ![アクセス許可。](media/permissions.png)

7. **[同意する]** を選択します。 

> [!NOTE]
> 同期は、LMS パートナーによって管理され、Microsoft グラフ API を使用してコース レベルで Teams チームにメンバーシップを同期するために使用される機能です。 これは主に、教育者がコース レベルで true としてオンに切り替える機能です。 その後、メンバーの追加または削除のために LMS 側で行われたメンバーシップの変更は、LMS パートナーによって実装された同期を使用して反映されます。 このプロセスが教育者に対して有効にされる前でさえ、M365 教育機関管理者は、以下に示す同期アクセス許可モーダルを使用して、教育者が同期にアクセスできます。 これらのアクセス許可は、LMS パートナーに付与され、教育者が LMS コースとクラス チーム間でメンバーシップTeamsできます。

8. トグルをオンにしてMicrosoft Teams同期を有効にします。

   ![teams-sync。](media/teams-sync.png)

## <a name="canvas-admin"></a>Canvas Admin

LTI 1.3 Microsoft Teamsをセットアップします。

Canvas Admin として、環境内に会議 LTI Microsoft Teamsを追加する必要があります。 アプリの LTI クライアント ID をメモします。

 - Microsoft Teams会議 - 170000000000703

1. Access **Admin settings**  >  **Apps**.

2. [+**アプリ] を** 選択して、LTI Teamsを追加します。

   ![外部アプリ。](media/external-apps.png)

3. 構成 **の種類として [クライアント ID 別** ] を選択します。

   ![アプリを追加します。](media/add-app.png)

4. 指定されたクライアント ID を入力し、[送信] を **選択します**。

   確認のためにクライアント ID のMicrosoft Teams LTI アプリ名が表示されます。

5. **[インストール]** を選択します。

   会議Microsoft Teams LTI アプリが外部アプリの一覧に追加されます。

6. Canvas 管理者アカウントの開発者キーに移動し、継承を選択し、会議のトグルを "オン" にすることで、アプリMicrosoft Teamsします。
   
## <a name="enable-for-canvas-courses"></a>キャンバス コースを有効にする

コース内で LTI を使用するには、Canvas コースの講師が統合同期を有効にする必要があります。各コースは、作成する対応するTeams教員が有効にする必要があります。作成のグローバルメカニズムTeamsはありません。 これは、不要なデータが作成されるのを防ぐためにTeams設計されています。

各コースで LTI[](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas)を有効にし、統合セットアップを完了するには、教員のドキュメントを参照してください。
