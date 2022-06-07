---
title: Canvas で Microsoft Teams クラスを使用する
ms.author: danismith
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
description: Microsoft Teams クラスと Canvas を統合する
ms.openlocfilehash: 10024e124ce50ab542e6e68a5c237a47e1f7af83
ms.sourcegitcommit: 8a0de6240facfe26ee391a14076b7fe534ee6598
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2022
ms.locfileid: "65923021"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Canvas で Microsoft Teams クラスを使用する

Microsoft Teams クラスはラーニング ツール相互運用性 (LTI) アプリであり、教育者と学生がラーニング管理システム (LMS) と Teams の間を簡単に移動するのに役立ちます。 ユーザーは、LMS 内から自分のコースに関連付けられているクラス チームに直接アクセスできます。

## <a name="prerequisites-before-deployment"></a>デプロイ前の前提条件

> [!NOTE]
> 現在の Teams クラス LTI では、限られたスコープ内の Canvas ユーザーと Microsoft Azure Active Directory (AAD) の同期のみがサポートされています。
>
> - テナントには Microsoft Education ライセンス (A1 以上) が必要です。
> - Canvas と Microsoft の間でユーザーをマッピングするために使用できる Microsoft テナントは 1 つだけです。
> - テナントは、キャンバス フィールド (電子メール、一意のユーザー ID、SIS ID、または統合 ID) と AAD (ユーザー プリンシパル名 (UPN)、プライマリ 電子メール アドレス (メール)、または電子メール エイリアス (mailNickname)) のフィールドの間で完全に一致している必要があります。
> - SDS を使用してクラスとグループを作成する場合は、SDS でチーム作成オプションを無効にし、クラスの重複を回避するために [グループ クリーンアップ](/schooldatasync/group-cleanup) を実行することをお勧めします。 SDS は、組織データとユーザー データを同期するために引き続き使用できます。

## <a name="enable-the-microsoft-teams-app-in-canvas"></a>キャンバスで Microsoft Teams アプリを有効にする

統合を開始するには、開発者キーを有効にし、Microsoft Teams Sync を有効にし、Microsoft-Teams-Sync-for-Canvas アプリを承認することで、Canvas でアプリを有効にする必要があります。 アプリの承認は、アプリを承認できる Microsoft テナント管理者のみが実行できることに注意してください。

**Microsoft Teams の同期を有効にして、アプリのアクセスを承認するには**:

1. 管理者として Canvas にサインインします。

2. グローバル ナビゲーションで **[管理者** ] リンクを選択し、アカウントを選択します。
3. 管理者ナビゲーションで、[ **開発者キー** ] リンクを選択し、[ **継承]** タブを選択します。
4. 展開する LTI アプリを有効にするには、適切な各アプリの **ON** 状態を選択します。

5. 管理者ナビゲーションで、[ **設定]** リンクを選択し、[統合] タブ **を** 選択します。

6. トグルをオンにして、Microsoft Teams 同期を有効にします。 この同期により、コースの登録に基づいて Teams でクラスを作成できます。

   ![Canvas Teams Sync の更新された png。](https://user-images.githubusercontent.com/87142492/128225881-abdfc52d-dc9e-48ad-aec5-f6617c6436f3.png)

7. 次のフィールドに適切な情報を入力します。 これらのフィールドは、Canvas のユーザーと AAD のユーザーの照合に使用されます。
   - **テナント名** は、Microsoft テナント名です。
   - **Login 属性** は、マッピングに使用される次の Canvas ユーザー属性の 1 つです。
      - **電子メール** は、Canvas ユーザーの既定のメール アドレスです。 ユーザーがキャンバスで既定のメール アドレスを変更した場合、コースへの登録が Teams との同期をブロックされる可能性があります。
      - **一意のユーザー ID** は、ユーザーの Canvas ログイン ID です。
      - **SIS ユーザー ID** は、学生情報システム (SIS) から設定され、ユーザーのプロファイル ページで表示できる ID 値です。
      - **統合 ID** は SIS インポートによってのみ設定され、ユーザーのプロファイル ページで表示できます。 通常、この一意の識別子は教育機関によって提供され、複数のアカウント間でユーザーを識別するためにアカウントの信頼またはコンソーシアムの状況で使用されます。

   - **サフィックス** フィールドは省略可能であり、Canvas 属性と Microsoft AAD フィールドの間に正確なマッピングがない場合にドメインを指定できます。 たとえば、Microsoft AAD の UPN が "name" である間にキャンバス電子メールが "name@example.edu" の場合は、サフィックス フィールドに 「@example.edu」と入力してユーザーと一致させることができます。 このフィールドには、前の @と共にドメインを入力する必要があります。
   - Active Directory ルックアップ属性は、キャンバス属性が一致する AAD のフィールドです。 UPN、プライマリ電子メール アドレス、または電子メール エイリアスの間で選択します。

8. [ **更新設定] を選択します**。

9. Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリのアクセスを承認するには、[ **テナント アクセスの許可** ] リンクを選択します。 Microsoft Identity Platform 管理者同意エンドポイントにリダイレクトされます。

   ![アクセス 許可。](media/permissions.png)

   > [!NOTE]
   > この手順は、アプリを承認できる Microsoft テナント管理者が実行する必要があります。

10. **[同意する]** を選択します。

## <a name="integrate-teams-classes-lti-in-canvas"></a>Teams クラス LTI をキャンバスに統合する

Azure アプリの同期と承認を有効にした後、Canvas 管理者は Teams クラス LTI アプリを Canvas 環境に追加して、Canvas ユーザー インターフェイスのナビゲーションに表示されるようになりました。

**Teams クラス LTI アプリを Canvas 環境に追加するには**、

1. **[管理者設定**] の [**アプリ**] タブで、[**+ アプリ**] を選択して Teams LTI アプリを追加します。

   ![external-apps。](media/external-apps.png)

2. **[構成の種類]** で、[**クライアント ID 別**] を選択します。

   ![アプリを追加します。](media/add-app.png)

3. **クライアント ID には**、Microsoft Teams クラス LTI **の170000000000570** を入力し、[送信] を選択 **します**。

4. 表示される確認で、アプリ名 (Microsoft Teams クラス) を確認し、[ **インストール**] を選択します。

   Microsoft Teams クラスの LTI アプリが外部アプリの一覧に追加されました。

## <a name="enabling-the-lti-app-for-canvas-courses"></a>Canvas コースの LTI アプリを有効にする

コース内で LTI アプリを使用するには、Canvas コースのインストラクターが統合同期を有効にする必要があります。各コースは、対応するチームを作成するためにインストラクターが有効にする必要があります。チームを作成するためのグローバル メカニズムはありません。 これは、不要なチームが作成されないようにするための予防措置として設計されています。

各コースで LTI アプリを有効にし、統合セットアップを完了するには、教師向け [ドキュメント](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) を参照してください。
