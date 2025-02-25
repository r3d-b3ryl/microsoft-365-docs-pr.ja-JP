---
title: Blackboard Learn Ultra で Microsoft Teams クラスを使用する
ms.author: danismith
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Blackboard Learn Ultra で Microsoft Teams クラスを使用します。
ms.openlocfilehash: 6e133b01dc2c70e87812e88590055fb48b6cbb99
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67275914"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a>Blackboard Learn Ultra で Microsoft Teams クラスを使用する

チームワークは、すべての現代組織の中核をなしています。 コラボレーションを促進することで、成功したすべての教育機関の特徴を定義できます。 Blackboard Learn Ultra のすべての機能と機能を強化するには、Microsoft Teams クラスとペアリングします。

クラスには、リアルタイムの会話、ビデオ会議、または非同期の対話が含まれる場合があります。 学生のファイル共有と共同作成エクスペリエンスを 1 か所で追加できます。 Learn Ultra の Microsoft Teams クラスは、教育のダイナミクスと効果的な学習の意味を再定義します。

> [!IMPORTANT]
> [学生情報システム (SIS)](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning) の [教育機関Email] フィールドが正常に設定されていることを確認します。
>
>Microsoft Teams クラスの統合は、SIS の教育機関の電子メール フィールドに依存して、正しいMicrosoft Azure Active Directory (AAD) [ユーザー 原則名 (UPN](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes)) にマップされます。 教育機関の電子メールがプロビジョニングされていない場合、これは既定で既存のメールに設定されます。 すべてのユーザーに対してこのフィールドを設定して、データが正しく同期されていることと、AAD と Blackboard Learn Ultra の間で電子メール データの競合がないことを確認することをお勧めします。
>
> SIS マッピングでこのフィールドを適切に設定していない場合、統合は引き続き機能しますが、作成された Teams クラスにユーザーが表示されず、エラーが発生する可能性があります。

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a>教育機関データ マッピングのサポート – 教育機関Email SIS フィールド

クラウド プロバイダー統合の進化の一環として、Blackboard Learn Ultra は、学生情報システム フレームワーク統合とパブリック REST API の両方で新しい **教育機関Email** フィールドを作成しました。これにより、教育機関は Blackboard Learn Ultra と AAD の間でデータ同期プロセスを効果的に管理できます。

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a>教育機関Email意味とサポート内容

**教育機関Email** フィールドを使用すると、クライアントの外部でサポートされているデータ ソースと Blackboard Learn Ultra の間でカスタマイズされたフィールド マッピングを行うことができます。 データ ソースが Microsoft などのクラウド プロバイダーの場合、ユーザー原則名 (UPN) は、UPN プレフィックス (ユーザーのアカウント名) と UPN サフィックス (DNS ドメイン名) と @記号で結合された各ユーザーのプライマリ一意識別子です。 これにより、Microsoft Azure Active Directory内の特定のユーザーごとに一意の電子メール アドレスが作成されます。

データが正確で、Blackboard Learn Ultra クラスと Microsoft Teams クラス間の登録またはメンバーシップが正しく達成されるようにするには、ユーザーの電子メール アドレスが両方のシステム間で一致している必要があります。 Blackboard Learn Ultra では、ユーザー インターフェイスで既存のメール アドレスを変更またはオーバーライドできます。これにより、同期エラーが発生し、ユーザーがクラス チームに正しく追加されない可能性があります。 **教育機関Email** フィールド マッピングを使用すると、ユーザーが Blackboard Learn Ultra 内でメールを変更したかどうかにかかわらず、このレベルのセキュリティと検証チェックを正しく管理できます。

 2 つの電子メール アドレスが異なる場合は、次のいずれかです。

- どのソースが優先順位を持ち、人物と教育機関の両方の電子メールとして取られるかを決定する必要があります。
  または
- 教育機関は、インスティテューション Emailでカスタム フィールド マッピングを設定できます。これにより、潜在的な競合を解決できます。

**教育機関Email** フィールド マッピングは、**Advanced Configuration Settings** > **Users Learn Object Type****Field Mapping** で既存のすべての SIS 統合タイプ > で使用できるようになりました。

> [!NOTE]
> 既定では、**教育機関Email** は、すべての SIS 形式の **Person Email** に設定され、各ユーザーに対して一意である必要があることに注意してください。 セットアップおよび実行されているすべての既存の統合には、SIS が電子メールが重複している場合にユーザーのインポートに失敗するため、このデータ マッピングが適用されます。 教育機関で教育機関のEmailを **カスタム** に変更する機能が必要な場合は、SIS の **高度な構成設定** を使用してこれを管理する必要があります。

## <a name="requirements"></a>要件

Microsoft Teams クラスの統合は、 **Ultra Course View コースでのみ** 使用できます。 教育機関で使用するには、次の要件を満たす必要があります。

- Ultra Base ナビゲーションが有効になっている Blackboard Learn Ultra Learn SaaS を使用する

  ![この機能の例はコースで有効になっています。](media/feature-availability.png)

- コースで使用するために LTI を有効にします。

  a. **管理者パネル** > **の LTI ツール プロバイダー****管理グローバル プロパティ** に > 移動します。

  b. **[コース] で [LTI が有効]** を選択し、必要に応じて [**組織で有効]** を選択します。

  c. **[送信]** を選択します。

- LTI が構成されている必要があります

- Blackboard Learn Ultra Teams クラス LTI 統合を追加する

- Microsoft Teams クラス LTI 1.3 ツールを追加する

- REST API ツールとクロスオリジン リソース共有を追加する

- Microsoft Teams クラス統合の構成と承認

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a>Blackboard Learn Ultra Teams クラス LTI 1.3 ツールを追加する

1. **管理者パネル** で、**LTI ツール プロバイダー** を選択します。

2. **LTI 1.3 ツールの登録** を選択します。

3. [ **クライアント ID** ] フィールドで、次の ID を入力またはコピーして貼り付けます。

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. 事前に設定されたすべての設定を確認し、[ **ツールの状態]** で [ **有効]** を選択します。

5. **教育機関ポリシー****で、[コース]、[名前]、[****Email アドレス**] の [ロール] を選択し、両方の [**はい**] を選択します。

6. [ **グレード サービス アクセスを許可する]** と [ **メンバーシップ サービス アクセスを許可する]** を選択します。

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a>Microsoft Teams クラス LTI 1.3 ツールを追加する

1. **管理者パネル** で、**LTI ツール プロバイダー** を選択します。

2. **LTI 1.3 ツールの登録** を選択します。

3. [ **クライアント ID** ] フィールドで、次の ID を入力またはコピーして貼り付けます。

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. 事前設定されているすべての設定を確認し、[ *ツールの状態]* で [ *有効] を選択します。*

5. **[教育機関ポリシー]** で、[コース]、[名前]、[**Email アドレス**] **の [ロール**] を選択します。 両方に **対して [はい** ] を選択します。

6. [ **グレード サービス アクセスを許可する]** と [ **メンバーシップ サービス アクセスを許可する]** を選択します。

## <a name="add-the-rest-api-tool"></a>REST API ツールを追加する

1. **[管理者] パネル** で [統合] に移動し、[**Rest API Integrations**] を選択します。

2. [ **統合の作成**] を選択します。

3. [ **アプリケーション ID** ] フィールドに、次の ID を入力またはコピーして貼り付けます。

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. この統合のユーザーを入力します。

   このユーザーは、アプリケーションが関連付けられているホーム API アクセス権を持つユーザーになります。

5. **[送信]** を選択します。

## <a name="add-the-cross-origin-resource-sharing"></a>クロスオリジン リソース共有を追加する

1. **[管理者] パネル** で [**統合**] に移動し、[**クロスオリジン リソース共有*] を選択します。

2. [ **構成の作成] を選択します**。

3. [ **配信元]** フィールドに、コピーの種類を入力し、次の URL を貼り付けます。

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. [ **許可されるヘッダー]** フィールドに「 **承認」** と入力します。

5. **[使用可能]** を **[はい**] に設定します。

6. **[送信]** を選択します。

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a>Microsoft Teams クラス統合の構成と承認

Blackboard Learn Ultra インスタンスを Microsoft Teams クラスと正常に統合するには、Blackboard Learn Ultra アプリケーションが Microsoft Azure テナント内でのアクセスが承認されていることを確認する必要があります。 これは、教育機関の Microsoft 365 Global 管理によって完了する必要があるプロセスです。

このプロセスは、Blackboard Learn Ultra Instance で LTI アプリケーションを構成する前または後に実行できます。

### <a name="before-configuring-the-lti-applications"></a>LTI アプリケーションを構成する前に

LTI 統合を構成する前に Blackboard Learn Ultra Teams Classes Azure アプリを承認することを選択した場合は、**Microsoft Identity Platform 管理 Consent Endpoint** にリダイレクトする必要があります。 URL が表示されます。

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> **{Tenant} を** 特定の教育機関の Microsoft Azure テナント ID に置き換えます。

Blackboard Learn Ultra に Microsoft Teams にアクセスするためのアクセス許可を付与していることを説明するアクセス許可ウィンドウが表示されます。

![Microsoft と Blackboard のアクセス許可ウィンドウ。](media/permissions1.png)

### <a name="after-configuring-the-lti-applications"></a>LTI アプリケーションを構成した後

1. **管理者パネル** で、[**ツールとユーティリティ]** に移動し、**Microsoft Teams 統合管理** を選択します。

2. [ **Microsoft Teams を有効にする]** を選択します。

3. 使用可能なテキスト フィールドに **Microsoft テナント ID を** 追加します。

4. 次のいずれかのオプションを選択します。

   - アプリに事前同意がある場合は、小さなチェックマークが表示されます。 チェックマークが表示された場合は、[送信] を選択 **します**。

   - 同意が承認されていない場合は、説明されている手順に従って同意用の URL を生成し、承認のために Microsoft 365 Global 管理に送信します。

5. 承認の確認が完了したら、[ **再試行** ] を選択して確認し、[送信] を選択 **します**。
