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
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: キャンバスMicrosoft Teamsクラスを統合する
ms.openlocfilehash: 77f17e8d64fe2bf565eff6c66aa00e9b566cf796
ms.sourcegitcommit: df1ad7118c4a95a310a4f17124322a6ae6ace26f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2021
ms.locfileid: "60268732"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Canvas でMicrosoft Teamsクラスを使用する

Microsoft Teamsクラスは、ラーニング ツール相互運用性 (LTI) アプリで、教育者と学生が ラーニング 管理システム (LMS) と Teams の間を簡単に移動するのに役立ちます。 ユーザーは、自分のコースに関連付けられているクラス チームに、自分の LMS 内から直接アクセスできます。

## <a name="prerequisites-before-deployment"></a>展開前の前提条件

> [!NOTE]
> 現在のTeamsクラス LTI では、Canvas ユーザーと制限されたスコープ内Microsoft Azure Active Directory (AAD) の同期のみをサポートします。 
> - テナントに Microsoft Education ライセンス (A1 以上) が必要です。
> - Canvas と Microsoft の間でユーザーをマッピングするには、1 つの Microsoft テナントのみを使用できます。
> - テナントは、キャンバス フィールド (電子メール、一意のユーザー ID、SIS ID、または統合 ID) と AAD (ユーザー プリンシパル名 (UPN)、プライマリ 電子メール アドレス (Mail)、または電子メール エイリアス (mailNickname)) のフィールドと完全に一致している必要があります。
> - SDS を使用してクラスとグループを作成する場合は、SDS でチーム作成オプションを無効にし[](/schooldatasync/group-cleanup)、クラスの重複を避けるためにグループ クリーンアップを実行することをお勧めします。 SDS を使用して、組織とユーザー データを同期できます。


## <a name="enable-the-microsoft-teams-app-in-canvas"></a>Canvas でMicrosoft Teamsアプリを有効にする
統合を開始するには、開発者キーを有効にし、Microsoft Teams Sync を有効にし、Microsoft-Teams-Sync-for-Canvas アプリを承認することで、Canvas でアプリを有効にする必要があります。 アプリの承認は、アプリを承認できる Microsoft テナント管理者によってのみ実行できます。

**アプリのMicrosoft Teamsの同期と承認を有効にするには**

1. 管理者として Canvas にサインインします。

2. グローバル ナビゲーション **で [管理者** ] リンクを選択し、アカウントを選択します。
3. 管理ナビゲーションで、[開発者キー] リンク **を選択** し、[継承] **タブを選択** します。
4. 展開する LTI アプリを有効にするには、該当する各アプリの **ON** 状態を選択します。

5. 管理ナビゲーションで、[リンク]**リンクを** 設定、[統合]**タブを選択** します。

6. トグルMicrosoft Teamsして同期を有効にします。 この同期により、コースの登録に基Teamsにクラスを作成できます。
   
   ![Canvas Teams更新された png を同期します。](https://user-images.githubusercontent.com/87142492/128225881-abdfc52d-dc9e-48ad-aec5-f6617c6436f3.png)

7. 次のフィールドに適切な情報を入力します。 これらのフィールドは、キャンバス内のユーザーとユーザーを一致AAD。 
   * テナント **名は** 、Microsoft テナント名です。
   * Login **Attribute は、** マッピングに使用される次の Canvas ユーザー属性の 1 つです。
      * **メール** は、Canvas ユーザーの既定のメール アドレスです。 ユーザーが Canvas で既定のメール アドレスを変更した場合、コースへの登録がユーザーの同期をブロックTeams。
      * **一意のユーザー ID** は、ユーザーの Canvas ログイン ID です。
      * **SIS ユーザー ID** は、学生情報システム (SIS) から入力され、ユーザーのプロファイル ページで表示できる ID 値です。
      * **統合 ID** は SIS インポートによってのみ設定され、ユーザーのプロファイル ページで表示できます。 通常、この一意の識別子は教育機関によって提供され、複数のアカウント間でユーザーを識別するためにアカウントの信頼またはコンソートの状況で使用されます。

   * サフィックス **フィールド** は省略可能で、Canvas 属性と Microsoft のフィールドの間に正確なマッピングが含AADできます。 たとえば、Microsoft AAD の UPN が 'name' の場合、キャンバスメールが 'name@example.edu' の場合は、接尾辞フィールドに '@example.edu' と入力してユーザーを一致できます。 ドメインは、前の @でこのフィールドに入力する必要があります。
   * Active Directory Lookup Attribute は、Canvas 属性AAD一致するフィールドです。 UPN、プライマリ メール アドレス、または電子メール エイリアスの間で選択します。

8. [更新 **] を設定** します。

9. Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリへのアクセスを承認するには、[テナント アクセスを **許可する] リンクを選択** します。 Microsoft Identity Platform Admin Consent Endpoint にリダイレクトされます。

   ![アクセス許可。](media/permissions.png)
> [!NOTE] 
> この手順は、アプリを承認できる Microsoft テナント管理者によって実行する必要があります。

10. **[同意する]** を選択します。

## <a name="integrate-teams-classes-lti-in-canvas"></a>キャンバスTeams LTI クラスを統合する

同期を有効にし、Azure アプリを承認すると、Canvas 管理者は Teams クラス LTI アプリをキャンバス環境に追加して、キャンバス ユーザー インターフェイスのナビゲーションに表示されます。

**キャンバス環境に Teams LTI アプリを追加するには**

1. [管理設定 **] の**[アプリ]**タブで****、[+ アプリ**] を選択して、LTI Teamsを追加します。

   ![外部アプリ。](media/external-apps.png)

3. [構成 **の種類] で**、[クライアント **ID 別] を選択します**。

   ![アプリを追加します。](media/add-app.png)

4. [**クライアント ID]****に、170000000000570** LTI Microsoft Teamsを入力し、[送信] を **選択します**。

5. 表示される確認で、アプリ名 (Microsoft Teams) を確認し、[インストール] を **選択します**。

   LTI Microsoft Teamsクラスが外部アプリの一覧に追加されました。
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a>キャンバス コースの LTI アプリを有効にする

コース内で LTI アプリを使用するには、Canvas コースの講師が統合同期を有効にする必要があります。各コースは、対応するチームを作成するために講師が有効にする必要があります。チームを作成するためのグローバルメカニズムはありません。 これは、望ましくないチームが作成されるのを防ぐための予防措置として設計されています。

各コースで LTI アプリを [有効](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) にし、統合セットアップを完了するには、教員のドキュメントを参照してください。
