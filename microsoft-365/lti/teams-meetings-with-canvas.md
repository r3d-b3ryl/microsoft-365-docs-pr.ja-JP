---
title: キャンバスでMicrosoft Teams会議を使用する
ms.author: danismith
author: DaniEASmith
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
description: Microsoft Teams会議を Canvas と統合する
ms.openlocfilehash: 59b4ee7a31d1c88f0417d2a9d3e0af1335155076
ms.sourcegitcommit: 997eb64f80da99b1099daba62994c722bbb25d72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2022
ms.locfileid: "66129165"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>キャンバスでMicrosoft Teams会議を使用する

Microsoft Teams会議は、教育者と学生がラーニング管理システム (LMS) とTeamsの間を簡単に移動するのに役立つラーニング ツール相互運用性 (LTI) アプリです。 ユーザーは、LMS 内から自分のコースに関連付けられているクラス チームに直接アクセスできます。

## <a name="prerequisites-before-deployment"></a>デプロイ前の前提条件

> [!NOTE]
> 現在のTeams会議 LTI では、限られたスコープ内でキャンバス ユーザーと Microsoft Azure Active Directory (AAD) の同期のみがサポートされています。
>
> - テナントには Microsoft Education ライセンスが必要です。
> - Canvas と Microsoft の間でユーザーをマッピングするために使用できる Microsoft テナントは 1 つだけです。
> - Canvas のMicrosoft Teams同期機能を Microsoft の学校データ同期 (SDS) と同時に使用する場合は、クラス名簿とクラス名簿データをSDS同期に含めないでください。引き続きSDSを使用して、ユーザー、組織、親連絡先、人口統計など、他のすべてのデータを同期できます。
> - **コース同期** を有効にせずに、Teams Meetings LTI を使用できます。ただし、[**クラス全体の追加]** オプションを使用することはできません。 出席者のメール アドレスを入力またはコピーして貼り付けるか、既存のチームのチャネルを会議に追加できます。

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 管理

Instructure Canvas 内でMicrosoft Teams統合を管理する前に、Canvas 管理者のセットアップを完了する前に、Microsoft Azure テナントの教育機関のMicrosoft Office 365管理者によって Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリが承認されている必要があります。

1. Canvas にサインインします。

2. グローバル ナビゲーションで **管理** リンクを選択し、アカウントを選択します。

3. 管理ナビゲーションで、**設定** リンクを選択し、[統合] タブ **を** 選択します。

   ![Canvas Teams Sync Updated png。](https://user-images.githubusercontent.com/87142492/128552407-78cb28e9-47cf-4026-954d-12dc3553af6f.png)

4. Microsoft テナント名、ログイン属性、ドメイン サフィックス、および AAD ルックアップ属性を入力します。 これらのフィールドは、Canvas のユーザーとMicrosoft Azure Active Directoryのユーザーの照合に使用されます。
   - Login 属性は、照合に使用される Canvas ユーザー属性です。
   - サフィックス フィールドは省略可能であり、Canvas 属性と Microsoft AAD フィールドの間に正確なマッピングがない場合にドメインを指定できます。 たとえば、Microsoft AAD の UPN が "name" の間にキャンバス電子メールが "name@example.edu" の場合は、サフィックス フィールドに「example.edu」と入力してユーザーを照合できます。
   - Active Directory 参照属性は、Canvas 属性が一致する Microsoft 側のフィールドです。 UPN、プライマリ電子メール アドレス、または電子メール エイリアスの間で選択します。

5. 完了したら **、[設定の更新]** を選択します。

6. Canvas の **Microsoft-Teams-Sync-for-Canvas** Azure アプリのアクセスを承認するには、[**テナント アクセスの許可**] リンクを選択します。 Microsoft Identity Platform 管理 Consent Endpoint にリダイレクトされます。

   ![アクセス 許可。](media/permissions.png)

7. **[同意する]** を選択します。

   > [!NOTE]
   > 同期は LMS パートナーによって管理される機能であり、Microsoft graph API を使用してコース レベルでメンバーシップをTeams チームに同期するために使用されます。 これは主に、教育者がコース レベルで true に切り替える機能です。 その後、LMS 側でメンバーの追加または削除に対して行われたメンバーシップの変更は、LMS パートナーによって実装された同期を使用して反映されます。 このプロセスが教育者に対して有効になる前であっても、M365 教育機関管理者は、以下の同期アクセス許可モーダルを使用して、教師が同期にアクセスできるようにします。 これらのアクセス許可は LMS パートナーに付与され、教育者は LMS コースと Teams クラス チームの間でメンバーシップを同期できます。

8. トグルをオンにして、Microsoft Teams同期を有効にします。

   ![teams-sync。](media/teams-sync.png)

## <a name="canvas-admin"></a>キャンバス 管理

Microsoft Teams LTI 1.3 統合を設定します。

Canvas 管理として、環境内にMicrosoft Teams会議 LTI アプリを追加する必要があります。 アプリの LTI クライアント ID をメモしておきます。

- Microsoft Teams会議 - 170000000000703

1. **アプリ管理設定** > にアクセス **します**。

2. **[+ アプリ] を** 選択して、Teams LTI アプリを追加します。

   ![external-apps。](media/external-apps.png)

3. 構成の種類 **として [クライアント ID 別** ] を選択します。

   ![アプリを追加します。](media/add-app.png)

4. 指定されたクライアント ID を入力し、[送信] を選択 **します**。

   確認のために、クライアント ID のMicrosoft Teams会議 LTI アプリ名が表示されます。

5. [**インストール**] を選択します。

   Microsoft Teams会議 LTI アプリが外部アプリの一覧に追加されます。

6. キャンバス管理者アカウントの開発者キーに移動し、継承を選択し、Microsoft Teams会議のトグルを "オン" にすることで、アプリを有効にします。

## <a name="enable-for-canvas-courses"></a>Canvas コースを有効にする

コース内で LTI を使用するには、Canvas コースのインストラクターが統合同期を有効にする必要があります。各コースは、対応するTeamsを作成するためにインストラクターによって有効にする必要があります。Teams作成のためのグローバル メカニズムはありません。 これは、不要なTeamsが作成されないように注意して設計されています。

各コースの LTI を有効にして統合セットアップを完了するには、教師向け [ドキュメント](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) を参照してください。
