---
title: Canvas でMicrosoft Teamsクラスを使用する
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
description: キャンバスMicrosoft Teamsクラスを統合する
ms.openlocfilehash: 8c19807034d5d063f71378dd450cfda419cd1491
ms.sourcegitcommit: e685fafd6dde4901c378685b423883faed7b4fe7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2021
ms.locfileid: "59460306"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Canvas でMicrosoft Teamsクラスを使用する

Microsoft Teamsクラスは、ラーニング ツール相互運用性 (LTI) アプリで、教育者と学生が ラーニング 管理システム (LMS) と Teams の間を簡単に移動するのに役立ちます。 ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。

## <a name="prerequisites-before-deployment"></a>展開前の前提条件

> [!NOTE]
> LTI の現在Teamsクラスは、キャンバス ユーザーと制限されたスコープ内Microsoft Azure Active Directory (AAD) の同期のみをサポートします。 
> - テナントに Microsoft Education ライセンスが必要です。
> - Canvas と Microsoft の間でユーザーをマッピングするには、1 つの Microsoft テナントのみを使用できます。
> - グループの重複を回避するには、学校データ同期 LTI を使用する前に、Teams (SDS) をオフにする必要があります。

## <a name="grant-admin-consent"></a>管理者の同意を付与する

Instructure Canvas 内で Microsoft Teams 統合を管理する前に、Canvas の **microsoft-Teams-Sync-for-Canvas** Azure アプリを、Microsoft Azure テナントの教育機関の Microsoft Office 365 管理者によって承認してから、Canvas 管理者のセットアップを完了することが重要です。 これらの手順を実行するには、グローバル管理者である必要があります。

1. [ページ] にAzure Active Directory。

2. アプリケーションEnterprise開き **、Microsoft-Teams-Sync-for-Canvas アプリケーションを選択** します。

3. [アクセス **許可] を** 選択し、[管理者の **同意を付与する] を選択します**。

4. アプリケーションに必要なアクセス許可に同意し、同意を与える。

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365管理者

1. Canvas にサインインします。

2. グローバル ナビゲーション **で [管理者** ] リンクを選択し、アカウントを選択します。

3. 管理ナビゲーションで、[リンク]**リンクを** 設定、[統合]**タブを選択** します。

4. トグルMicrosoft Teamsして同期を有効にします。
   
   ![Canvas Teams更新された png を同期します。](https://user-images.githubusercontent.com/87142492/128225881-abdfc52d-dc9e-48ad-aec5-f6617c6436f3.png)

5. Microsoft テナント名、login 属性、ドメイン サフィックス、および AAD 参照属性を入力します。

   これらのフィールドは、キャンバス内のユーザーとユーザーの照合に使用Microsoft Azure Active Directory。 
   * Login Attribute は、照合に使用される Canvas ユーザー属性です。
   * サフィックス フィールドは省略可能で、Canvas 属性と Microsoft AAD フィールドの間に正確なマッピングが設定されていない場合にドメインを指定できます。 たとえば、Microsoft AAD の UPN が 'name' の場合、Canvas メールが 'name@example.edu' の場合は、接尾辞フィールドに 「example.edu」 と入力してユーザーを一致できます。
   * Active Directory Lookup Attribute は、Canvas 属性が一致する Microsoft 側のフィールドです。 UPN、プライマリ メール アドレス、または電子メール エイリアスの間で選択します。

6. [完了 **したら設定** 更新] を選択します。

7. Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリへのアクセスを承認するには、[テナント アクセスを **許可する] リンクを選択** します。 Microsoft Identity Platform Admin Consent Endpoint にリダイレクトされます。

   ![アクセス許可。](media/permissions.png)

8. **[同意する]** を選択します。

## <a name="canvas-admin"></a>Canvas Admin

LTI 1.3 Microsoft Teamsをセットアップします。

Canvas 管理者として、環境内に LTI Microsoft Teamsクラスを追加する必要があります。 メイン アカウントの開発者キーの一覧にアクセスし、継承されたキーに切り替えて、LTI ツールTeams有効にします。 アプリの LTI クライアント ID をメモします。

 - Microsoft Teamsクラス - 170000000000570

1. Access **Admin settings**  >  **Apps**.

2. [+**アプリ] を** 選択して、LTI Teamsを追加します。

   ![外部アプリ。](media/external-apps.png)

3. 構成 **の種類として [クライアント ID 別** ] を選択します。

   ![アプリを追加します。](media/add-app.png)

4. 指定されたクライアント ID を入力し、[送信] を **選択します**。

   確認のためにクライアント ID Microsoft Teamsクラス LTI アプリ名が表示されます。

5. **[インストール]** を選択します。

   LTI Microsoft Teamsクラスは、外部アプリの一覧に追加されます。
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a>キャンバス コースの LTI アプリを有効にする

コース内で LTI アプリを使用するには、Canvas コースの講師が統合同期を有効にする必要があります。各コースは、対応するチームを作成するために講師が有効にする必要があります。チームを作成するためのグローバルメカニズムはありません。 これは、望ましくないチームが作成されるのを防ぐための予防措置として設計されています。

各コースで LTI アプリを [有効](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) にし、統合セットアップを完了するには、教員のドキュメントを参照してください。
