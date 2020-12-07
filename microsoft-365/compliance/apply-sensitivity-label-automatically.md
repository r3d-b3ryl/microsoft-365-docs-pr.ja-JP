---
title: 機密ラベルをコンテンツに自動的に適用する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
description: 機密ラベルを作成する場合、ドキュメントまたは電子メールにラベルを自動的に割り当てるか、あるいは推奨するラベルを選択するようにユーザーに求めることができます。
ms.openlocfilehash: 705752a63d3cd1ca5f6950643648ba5c3dd50336
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551348"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>機密ラベルをコンテンツに自動的に適用する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

機密ラベルを作成する場合、指定した条件に一致したときに、そのラベルをコンテンツに自動的に割り当てることができます。

機密ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。

- ユーザーのトレーニングは、一部の分類方法をいつ使用するかについてのみ必要。

- ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。

- ユーザーはポリシーについて把握する必要がなくなり、自分たちの仕事に集中できます。

コンテンツが手動でラベル付けされている場合、そのラベルが自動ラベル付けで置き換えられることはありません。 ただし、自動ラベル付けは、自動的に適用された[優先度が低いラベル](sensitivity-labels.md#label-priority-order-matters)を置き換えることができます。

機密ラベルを自動的に適用するには、次の 2 つの異なる方法があります。

- **ユーザーがドキュメントを編集したり、メールを作成 (返信または転送) するときのクライアント側のラベル付け**: Office アプリ (Word、Excel、PowerPoint、Outlook) の自動ラベル付け用に構成されたラベルを使用します。 
    
    この方法は、ユーザーへのラベルの推奨と、ラベルの自動適用をサポートしています。 ただし、どちらの場合も、ユーザーはラベルを承諾または拒否するかどうかを決定し、コンテンツの正しいラベル付けを行います。 このクライアント側のラベル付けでは、ドキュメントを保存する前であってもラベルを適用できるため、ドキュメントの遅延が最小限に抑えられます。 ただし、すべてのクライアント アプリが自動ラベル付けをサポートしているわけではありません。 この機能は、Azure Information Protection 統合ラベル付けクライアント、および [Office の一部のバージョン](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)でサポートされています。 
    
    構成手順については、このページの「[Office アプリの自動ラベル付けを構成する方法](#how-to-configure-auto-labeling-for-office-apps)」を参照してください。

- **コンテンツが既に保存されている (SharePoint または OneDrive で) またはメールで送信された (Exchange Online によって処理される) サービス側のラベル付け**: 自動ラベル付けポリシーを使用します。 
    
    この方法は、保存データ (SharePoint および OneDrive のドキュメント) や転送中のデータ (Exchange によって送信または受信されたメール) の自動ラベル付けと呼ばれることもあります。 Exchange の場合、保存されているメール (メールボックス) は含まれません。 
    
    このラベル付けはアプリケーションではなくサービスによって適用されるため、ユーザーが使用しているアプリやバージョンを気にする必要はありません。 その結果、この機能は、組織全体ですぐに使用できるようになります。また、規模に応じたラベル付けに適しています。 自動ラベル付けポリシーでは、ユーザーがラベル付けプロセスを操作しないので、推奨されるラベル付けをサポートしていません。 代わりに、管理者は、実際にラベルを適用する前に、コンテンツの正しいラベル付けを行うために、シミュレーション モードでポリシーを実行します。
    
    構成手順については、このページの「[SharePoint、OneDrive、Exchange の自動ラベル付けポリシーを構成する方法](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)」を参照してください。
    
    SharePoint と OneDrive の自動ラベル付けに固有:
    - Word、PowerPoint、Excel の Office ファイルがサポートされています。 Open XML 形式 (.docx や .xlsx など) はサポートされていますが、Microsoft Office 97-2003 形式 (.doc や .xls など) はサポートされていません。
    - テナント内で 1 日あたり最大 25,000 個の自動的にラベル付けされたファイル。
    - テナントあたり最大 10 個の自動ラベル付けポリシーが作成されます。各ポリシーは、最大 10 サイト (SharePoint サイトまたは OneDrive サイト) を対象としています。
    - シミュレーション モードの場合、およびラベルが適用される場合、自動ラベル付けポリシーの結果として、変更、変更者、変更日の既存の値は変更されません。
    - ラベルが暗号化を適用する場合、[Rights Management 発行者と Rights Management 所有者](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) は、ファイルを最後に変更したアカウントです。

    Exchange の自動ラベル付けに固有:
    - 手動でのラベル付けや Office アプリを使用した自動ラベル付けとは異なり、Office の添付ファイル (Word、Excel、PowerPoint ファイル) および PDF の添付ファイルも自動ラベル付けポリシーで指定した条件に合わせてスキャンされます。 一致がある場合、メールにはラベルが付けられますが、添付ファイルにはラベルが付けられません。
        - Office ファイルの場合、Open XML 形式 (.docx や .xlsx など) はサポートされていますが、Microsoft Office 97-2003 形式 (.doc や .xls など) はサポートされていません。
    - IRM 暗号化を適用する Exchange メール フロー ルールまたはデータ損失防止 (DLP) ポリシーがある場合: これらのルールやポリシーおよび自動ラベル付けポリシーによってコンテンツが識別されると、ラベルが適用されます。 このラベルが暗号化を適用すると、Exchange メール フロー ルールまたは DLP ポリシーの IRM 設定は無視されます。 ただし、そのラベルが暗号化を適用しない場合、メール フロー ルールまたは DLP ポリシーの IRM 設定がラベルに加えて適用されます。
    - ラベルが表示されない IRM 暗号化を使用しているメールは、自動ラベル付けを使用すると一致する場合は、暗号化設定のあるラベルに置き換えられます。
    - 自動ラベル付け条件と一致すると、受信メールにラベルが付けられます。 ただし、ラベルが暗号化用に構成されている場合、その暗号化は適用されません。
    - ラベルが暗号化を適用する場合、[Rights Management 発行者と Rights Management 所有者](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) は、メールを送信するユーザーです。
    

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a>Office アプリの自動ラベル付けと自動ラベル付けポリシーを比較する

次の表は、2 つの相補的な自動ラベル付け方法の違いを特定するのに役立ちます。

|機能または動作|ラベル設定: Office アプリの自動ラベル付け |ポリシー: 自動ラベル付け|
|:-----|:-----|:-----|
|アプリの依存関係|[はい](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps) |いいえ \* |
|場所による制限|いいえ |はい |
|条件: トレーニング可能な分類子|はい |いいえ |
|条件: メールの共有オプションと追加オプション|いいえ |はい |
|推奨事項、ポリシーのヒント、ユーザー上書き|はい |いいえ |
|シミュレーション モード|いいえ |はい |
|条件についてチェックされた Exchange 添付ファイル|いいえ | はい|
|視覚的なマーキングの適用 |はい |はい (メール専用) |
|ラベルなしで適用された IRM 暗号化の上書き|はい (ユーザーがエクスポートの最小使用権を持っている場合) |はい (メール専用) |
|受信メールのラベル付け|いいえ |はい (暗号化は適用されません) |

\* 自動ラベル付けは、現在、一部の地域では利用できません。 テナントがこの機能をサポートできない場合、自動ラベル付けタブは管理ラベル センターに表示されません。

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>複数のラベルに適用するときの複数の条件の評価方法

ラベルは、ポリシー内で指定した位置に従って評価の順序を決められます。先頭に配置したラベルが最下位 (機密性が最も低い) になり、最後に配置したラベルが最上位 (機密性が最も高い) になります。優先度に関する詳細については、「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>自動適用または推奨されるように親ラベルを構成しない

親ラベル (サブラベルのあるラベル) はコンテンツに適用できません。 Office アプリで親ラベルが自動適用または自動推奨されるように構成されていないこと、自動ラベル ポリシーで親ラベルが選択されていないことを確認してください。 その場合、親ラベルをコンテンツに適用できなくなる可能性があります。

自動ラベルでサブラベルも使用するには、必ず親ラベルとサブラベルの両方を発行してください。

親ラベルとサブラベルの詳細については、「[サブラベル (ラベルのグループ化)](sensitivity-labels.md#sublabels-grouping-labels)」を参照してください。

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>Office アプリの自動ラベル付けを構成する方法

Windows 用 Office アプリの自動ラベル付けは、Azure Information Protection 統合ラベル付けクライアントでサポートされています。 Office アプリのラベルが内蔵されている場合、この機能は、[さまざまなアプリの可用性のさまざまな段階にあります](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)。

Office アプリの自動ラベル付け設定は、[機密ラベルを作成または編集する](create-sensitivity-labels.md)ときに使用できます。 ラベルのスコープとして **[ファイルとメール]** が選択されていることを確認してください。 

![ファイルとメールの秘密度レベル スコープ オプション](../media/filesandemails-scope-options-sensitivity-label.png)

ウィザードを移動すると、**[Office アプリの自動ラベル付け]** ページが表示されます。このページでは、機密情報の種類またはトレーニング可能な分類子のリストから選択できます。

![Office アプリの自動ラベル付けのラベル条件](../media/sensitivity-labels-conditions.png)

この機密ラベルが自動的に適用されると、ユーザーの Office アプリに通知が表示されます。 例:

![ドキュメントにラベルが自動適用されたという通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a>ラベルの機密情報の種類の構成

**機密情報の種類** オプションを選択すると、データ損失防止 (DLP) ポリシーを作成するときと同じ機密情報の種類の一覧が表示されます。 そのため、たとえば、クレジットカード番号、社会保障番号、またはパスポート番号など、お客様の個人情報を含むコンテンツに極秘ラベルを自動的に適用できます。

![Officeアプリの自動ラベル付け用の機密情報の種類](../media/sensitivity-labels-sensitive-info-types.png)

機密情報の種類を選択した後は、インスタンス数または一致精度を変更して条件を絞り込むことができます。 詳細については、「[一致の難易度を設定するためのルールの調整](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」を参照してください。

さらに、条件で検知する必要があるのは、機密情報の種類のすべてか、またはそのうちの 1 つだけかを選択できます。 また、条件をより柔軟または複雑にするには、グループを追加し、グループ間で論理演算子を使用できます。 詳細については、「[グループ化および論理演算子](data-loss-prevention-policies.md#grouping-and-logical-operators)」を参照してください。

![インスタンス数と一致精度のオプション](../media/Sensitivity-labels-instance-count-match-accuracy.png)

### <a name="configuring-trainable-classifiers-for-a-label"></a>ラベルのトレーニング可能な分類子を構成する

このオプションは現在プレビューの段階です。

**トレーニング可能な分類子** のオプションを選択する場合、Microsoft から 1 つ以上のトレーニング可能な組み込み分類子を選択します。 独自のトレーニング可能なカスタム分類子を作成している場合は、以下を選択できます。

![トレーニング可能な分類子と秘密度ラベルのオプション](../media/sensitivity-labels-classifers.png)

> [!CAUTION]
> 組み込みの [**不快な言葉**] は、誤検知の数が多いため、廃止予定です。 この組み込み分類子を使用しないでください。現在使用している場合は、ビジネス プロセスを移動する必要があります。 代わりに、[**個人を標的にしたハラスメント**]、[**冒涜的表現**]、および [**脅威**] の組み込み分類子を使用することをお勧めします。

これらの分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の詳細](classifier-learn-about.md)」を参照してください。

このオプションのプレビュー期間中は、次のアプリが秘密度ラベルのトレーニング可能な分類子をサポートします。

- Microsoft 365 Apps for enterprise ([以前の Office 365 ProPlus](https://docs.microsoft.com/deployoffice/name-change)) for Windows は、現在、バージョン 2006 以降で[最新機能提供チャネル](https://docs.microsoft.com/deployoffice/overview-update-channels#current-channel-overview) に展開中です。
    - Word
    - Excel
    - PowerPoint

- [SharePoint および OneDrive で Office ファイルの秘密度ラベルを有効にする機能 (パブリック プレビュー)](sensitivity-labels-sharepoint-onedrive-files.md) が有効になっている場合の Web アプリ用の Office:
    - Word
    - Excel
    - PowerPoint
    - Outlook

### <a name="recommend-that-the-user-applies-a-sensitivity-label"></a>ユーザーが秘密度ラベルを適用することを推奨

状況に応じて、ユーザーがラベルを適用することを推奨できます。 このオプションでは、分類および関連する保護を受け入れるか、またはラベルがそのコンテンツに適していない場合、推奨事項を無視するかをユーザーが選択できます。

![機密ラベルをユーザーに推奨するためのオプション](../media/Sensitivity-labels-Recommended-label-option.png)

ラベルを推奨される操作として適用するように条件を構成したときの、Azure Information Protection の統合ラベル付けクライアントからのプロンプトの例を、カスタム ポリシー ヒントと共に示します。ポリシー ヒントに表示するテキストを選択できます。

![推奨ラベルを適用するためのプロンプト](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied"></a>自動ラベルまたは推奨ラベルが適用されている場合

Office アプリでの自動ラベル付けと推奨ラベル付けの実装は、Office に組み込まれているラベル付けを使用しているか、または Azure Information Protection の統合ラベル付けクライアントを使用しているかによって異なります。 ただし、どちらの場合も次のようになります。

- 以前に手動でラベルが付けられているか、以前に上位の機密度で自動的にラベルが付けられているドキュメントと電子メールには自動ラベル付けを使用できません。 ドキュメントや電子メールに適用できる機密ラベルは (1 つの保持ラベルに加えて) 1 つだけであることにご注意ください。

- 以前に上位の秘密度でラベルが付けられているドキュメントまたはメールには推奨ラベル付けを使用できません。 コンテンツに既に上位の秘密度でラベルが付けられている場合、推奨事項とポリシー ヒントに関するプロンプトは、ユーザーに表示されません。

組み込みのラベル付けに関してのみ以下の点が当てはまります。

- 必ずしもすべての Office アプリで自動 (および推奨) ラベル付けがサポートされるわけではありません。 詳しくは、「[アプリでの秘密度ラベル機能のサポート](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)」を参照してください。

- Word のデスクトップ バージョンにおける推奨ラベルでは、推奨をトリガーした機密コンテンツにフラグが付けられるので、ユーザーが確認して、推奨されている秘密度ラベルを適用しないで機密コンテンツを削除できます。

- こうしたラベルが Office アプリで適用される方法、スクリーンショット例、機密情報の検出方法について詳しくは、「[Office のファイルとメールに秘密度ラベルを自動的に適用、または推奨する](https://support.office.com/ja-JP/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)」を参照してください。

Azure Information Protection 統合ラベル付けクライアントに関してのみ以下の点が当てはまります。

-  自動ラベル付けと推奨ラベル付けは、Word、Excel、PowerPoint でドキュメントが保存されるときと、Outlook でメールが送信されるときに適用されます。

- Outlook で推奨ラベル付けをサポートするには、最初に[詳細なポリシー設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)を構成する必要があります。

- ドキュメントやメール内の本文、およびヘッダーとフッターに含まれる機密情報が検出されますが、件名やメールの添付ファイルのものは検知されません。

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a>SharePoint、OneDrive、Exchange の自動ラベル付けポリシーを構成する方法

自動ラベル付けポリシーを構成する前に、前提条件を必ずご確認ください。 

### <a name="prerequisites-for-auto-labeling-policies"></a>自動ラベル付けポリシーの前提条件

- シミュレーション モード:
    - Microsoft 365 の監査を有効にする必要があります。 監査を有効にする必要がある場合、または監査が既に有効になっているかどうかが不明の場合は、「[監査ログの検索を有効または無効にする](turn-audit-log-search-on-or-off.md)」を参照してください。
    - ソース ビューでファイルの内容を表示するには、**コンテンツ エクスプローラーのコンテンツ閲覧者** の役割が必要です。 既定では、全体管理者にはこの役割はありません。 このアクセス許可がない場合、[**一致したアイテム**] タブからアイテムを選択してもプレビュー ウィンドウは表示されません。

- SharePoint および OneDrive にあるファイルに自動でラベルを付けるには:
    - [SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にしています](sensitivity-labels-sharepoint-onedrive-files.md)。
    - 自動ラベル付けポリシーの実行時に、別のプロセスまたはユーザーがファイルを開いておくことはできません。 編集用にチェックアウトされたファイルは、このカテゴリに分類されます。

- 組み込みの機密度の種類ではなく、[カスタムの機密情報の種類](custom-sensitive-info-types.md)を使用する場合は、次の操作を行います。 
    - カスタム機密情報の種類は、カスタム機密情報の種類が保存された後に SharePoint または OneDrive に追加されたコンテンツに対して評価されます。 
    - 新しいカスタムの機密情報の種類をテストするには、自動ラベル付けポリシーを作成する前に作成してから、テスト用のサンプル データを使用して新しいドキュメントを作成します。

- 自動ラベル付けポリシー用に選択できる、[作成および公開された](create-sensitivity-labels.md) (少なくとも 1 人のユーザーに対して) 1 つ以上の秘密度ラベル。 これらのラベルの場合:
    - 概要で説明したように、ラベル設定は自動ラベル付けポリシーを補完するため、Office アプリのラベル設定の自動ラベル付けがオンかオフかは関係ありません。
    - 自動ラベル付けに使用するラベルが視覚的なマーキング (ヘッダー、フッター、透かし) を使用するように構成されている場合、これらはドキュメントに適用されないことに注意してください。
    - ラベルに [暗号化](encryption-sensitivity-labels.md)を適用する場合は、**[今すぐアクセス許可を適用する]** の設定を構成する必要があります。

### <a name="learn-about-simulation-mode"></a>シミュレーション モードの詳細

シミュレーション モードは、自動ラベル付けポリシーに固有であり、ワークフローに組み込まれています。 ポリシーによって少なくとも 1 つのシミュレーションが実行されるまで、ドキュメントとメールに自動的にラベルを付けることはできません。

自動ラベル付けポリシーのワークフロー:

1. 自動ラベル付けポリシーを作成して構成する。

2. ポリシーをシミュレーション モードで実行し、24時間後、またはシミュレーションが完了するまで待機します。

3. 結果を確認し、必要に応じてポリシーを調整します。 シミュレーション モードを再実行し、24時間後、またはシミュレーションが完了するまで待機します。

4. 必要に応じて、手順 3 を繰り返します。

5. 実稼働環境に展開する。

シミュレーションされた展開は、PowerShell の WhatIf パラメーターのように動作します。 定義したルールを使用して、自動ラベル付けポリシーが選択したラベルを適用したかのようにレポートされた結果が表示されます。 その後、必要に応じてルールの精度を高め、シミュレーションを再実行できます。 ただし、Exchange の自動ラベル付けは、メールボックスに保存されたメールではなく、送受信されるメールに適用されるため、完全に同じメール メッセージを送受信することができなければ、シミュレーションのメールの結果に一貫性があるとは期待できません。

シミュレーション モードでは、展開前に自動ラベル付けポリシーの範囲を徐々に広げることもできます。 たとえば、1 つのドキュメント ライブラリを持った SharePoint サイトなどの 1 つの場所から始めることができます。 次に、反復的な変更を加えて、範囲を複数のサイトに拡大し、次に OneDrive などの別の場所に拡大します。

最後に、シミュレーション モードを使用して、自動ラベル付けポリシーの実行に必要な時間の概算を提供し、シミュレーション モードを使用せずに実行するタイミングを計画してスケジュールすることができます。

### <a name="creating-an-auto-labeling-policy"></a>自動ラベル付けポリシーの作成

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com/)で、機密ラベルに移動します。
    
    - [**ソリューション**]  >  [**Information Protection**]
    
    このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。

2. [**自動ラベル付け**] タブを選択します。
    
    ![自動ラベル付け](../media/auto-labeling-tab.png)
    
    > [!NOTE]
    > **[自動ラベル付け]** タブが表示されない場合、この機能は現在お住まいの地域ではご利用いただけません。

3. [**+自動ラベル付けポリシーの作成**] を選択します。 これにより、新しいポリシー ウィザードが起動します。
    
    ![自動ラベル付け用の新しいポリシー ウィザード ](../media/auto-labeling-wizard.png)

4. [**このラベルを適用する情報を選択する**] ページの場合: [**財務**] または [**プライバシー**] などのテンプレートのいずれかを選択します。 ドロップダウンの **表示オプション** を使用して、検索を絞り込むことができます。 または、テンプレートが要件を満たしていない場合は、[**カスタム ポリシー**] を選択します。 [**次へ**] を選択します。

5. [**自動ラベル ポリシーに名前を付ける**] ページの場合: 一意の名前を入力し、必要に応じて説明を入力して、自動的に適用されるラベル、場所、ラベル付けするコンテンツを識別する条件を識別します。

6. [**ラベルを適用する場所を選択する**] ページの場合: Exchange、SharePoint サイト、OneDrive の場所を選択して指定します。 [**次へ**] を選択します。
    
    ![[場所の選択] ページの自動ラベル付けウィザード ](../media/locations-auto-labeling-wizard.png)
    
    個々の SharePoint サイトと OneDrive アカウントを指定する必要があります。 OneDrive の場合、ユーザーの OneDrive アカウントの URL は次の形式になります。`https://<tenant name>-my.sharepoint.com/personal/<user_name>_<tenant name>_com`
    
    たとえば、「rsimone」のユーザー名を持つ contoso テナント内のユーザーの場合: `https://contoso-my.sharepoint.com/personal/rsimone_contoso_onmicrosoft_com`
    
    テナントの構文を確認し、ユーザーの URL を特定するには、「[組織内のすべてのユーザーの OneDrive URL のリストを取得する](https://docs.microsoft.com/onedrive/list-onedrive-urls)」を参照してください。

7. [**一般または詳細ルールの設定**] ページの場合: 既定の [**一般的なルール**] のままにして、選択したすべての場所でラベル付けするコンテンツを識別するルールを定義します。 場所ごとに異なるルールが必要な場合は、[**詳細ルール**] を選択します。 [**次へ**] を選択します。
    
    ルールでは、機密情報の種類と共有オプションを含む条件を使用します。
    - 機密情報の種類については、組み込みとカスタムの両方の機密情報の種類を選択できます。
    - 共有オプションについては、[**組織内の連絡先のみ**] または [**組織外の連絡先**] を選択できます。
    
    唯一の場所が **Exchange** である場合、または [**詳細ルール**] を選択した場合、次のような選択ができる追加の条件があります。
    - 送信者の IP アドレスが
    - 受信者ドメインが
    - 受信者が
    - 添付ファイルの拡張子が
    - 添付ファイルがパスワードで保護されている
    - メールの添付ファイルのコンテンツをスキャンできなかった
    - メールの添付ファイルのコンテンツのスキャンが完了しなかった

8. 以前の選択に応じて、条件と例外を使用して新しいルールを作成する機会があります。
    
    機密情報の種類の構成オプションは、Office アプリの自動ラベル付けに選択したものと同じです。 詳細情報が必要な場合は、「[ラベルの機密情報の種類の構成](#configuring-sensitive-info-types-for-a-label)」を参照してください。
    
    必要なすべてのルールを定義し、状態が [オン] になっていることを確認したら、[**次へ**] を選択して、自動適用するラベルの選択に進みます。

11. [**自動適用するラベルを選択する**] ページの場合: [**+ ラベルの選択**] を選択し、[**機密ラベルの選択**] ウィンドウのラベルを選択し、[**次へ**] を選択します。

12. **[ポリシーを今すぐテストするか後でテストするかを決定する]** ページの場合: シミュレーション モードで、今すぐ自動ラベル付けポリシーを実行する準備が整っている場合は、**[シミュレーション モードでポリシーを実行する]** を選択します。 それ以外の場合は、**[ポリシーをオフのままにする]** を選択します。 [**次へ**] を選択します。 
    
    ![ポリシーの自動ラベル付けウィザードをテストする](../media/simulation-mode-auto-labeling-wizard.png)

13. **[概要]** ページの場合: 自動ラベル付けポリシーの構成を確認し、必要な変更を行い、ウィザードを完了します。
    
    Office アプリの自動ラベル付けとは異なり、個別の公開オプションはありません。 ただし、ラベルの公開と同様に、自動ラベル付けポリシーが組織全体に複製されるまでに最大 24 時間かかります。

**[情報保護]** > **[自動ラベル付け]** ページでは、自動ラベル付けポリシーを **[シミュレーション]** または **[オフ]** セクションのどちらかで確認できます。これは、シミュレーション モードで実行することを選択したかどうかによって決まります。 ポリシーを選択して、構成と状態の詳細 (**[ポリシー シミュレーションの実行中]** など) を確認します。 シミュレーション モードのポリシーの場合は、**[一致したアイテム]** タブを選択して、指定したルールに一致した電子メールまたはドキュメントを確認します。

このインターフェイスからは、次のようにポリシーを直接変更できます。

- **[オフ]** セクションのポリシーの場合は、**[ポリシーの編集]** ボタンを選択します。

- **[シミュレーション]** セクションのポリシーの場合は、いずれかのタブからページの上部にある **[ポリシーの編集]** オプションを選択します。
    
    ![自動ラベル付けポリシーの編集オプション](../media/auto-labeling-edit.png)
    
    シミュレーションなしでポリシーを実行する準備が整っているときには、**[ポリシーを有効にする]** オプションを選択します。

自動ポリシーは、削除されるまで継続的に実行されます。 たとえば、新しいドキュメントや変更されたドキュメントは、現在のポリシー設定に含まれます。

また、適切な[アクセス許可](data-classification-content-explorer.md#permissions)がある場合は、[コンテンツ エクスプローラー](data-classification-content-explorer.md)を使用して、自動ラベル付けポリシーの結果を確認することもできます。
- **コンテンツ エクスプローラーのリスト閲覧者** では、ファイルのラベルは表示できますが、ファイルのコンテンツは表示できません。
- **コンテンツ エクスプローラーのコンテンツ閲覧者** では、ファイルの内容を表示できます。

> [!TIP]
> コンテンツ エクスプローラーを使用して、機密情報を含むラベルの付いていないドキュメントがある場所を特定することもできます。 この情報を使用して、自動ラベル付けポリシーにこれらの場所を追加することを検討し、識別された機密情報の種類をルールとして含めます。

### <a name="use-powershell-for-auto-labeling-policies"></a>自動ラベル付けポリシーに PowerShell を使用する

[セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell) を使用して、自動ラベル付けポリシーを作成し、構成できるようになりました。 これにより、自動ラベル付けポリシーの作成やメンテナンスを完全にスクリプト化できるようになり、OneDrive や SharePoint の場所に複数の URL を指定する効率的な方法も提供されるようになりました。

PowerShell でコマンドを実行する前に、最初に[セキュリティ/コンプライアンス センターの PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)する必要があります。

新しい自動ラベル付けポリシーを作成するには: 

```powershell
New-AutoSensitivityLabelPolicy -Name <AutoLabelingPolicyName> -SharePointLocation "<SharePointSiteLocation>" -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```
このコマンドは、指定した SharePoint サイトの自動ラベル付けポリシーを作成します。 OneDrive の場所については、代わりに *OneDriveLocation* パラメーターを使用します。 

既存の自動ラベル付けポリシーにサイトを追加するには:

```powershell
$spoLocations = @("<SharePointSiteLocation1>","<SharePointSiteLocation2>")
Set-AutoSensitivityLabelPolicy -Identity <AutoLabelingPolicyName> -AddSharePointLocation $spoLocations -ApplySensitivityLabel <Label> -Mode TestWithoutNotifications
```

このコマンドは、追加の SharePoint URL を変数に指定し、既存の自動ラベル付けポリシーに追加します。 代わりに OneDrive の場所を追加するには、*AddOneDriveLocation* パラメーターに *$OneDriveLocations* のような別の変数を指定して使用します。

新しい自動ラベル付けポリシー ルールを作成するには:

```powershell
New-AutoSensitivityLabelRule -Policy <AutoLabelingPolicyName> -Name <AutoLabelingRuleName> -ContentContainsSensitiveInformation @{"name"= "a44669fe-0d48-453d-a9b1-2cc83f2cba77"; "mincount" = "2"} -Workload SharePoint
```

既存の自動ラベル付けポリシーについては、このコマンドはエンティティ ID が a44669fe-0d48-453d-a9b1-2cc83f2cba77 である **米国の社会保障番号 (SSN)** の機密情報の種類を検出するための新しいポリシー ルールを作成します。 その他の機密情報の種類のエンティティ ID を検索するには、「[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)」を参照してください。

自動ラベル付けポリシーをサポートする PowerShell コマンドレット、使用可能なパラメーター、そしていくつかの例の詳細については、次のコマンドレットのヘルプを参照してください。

- [Get-AutoSensitivityLabelPolicy](https://docs.microsoft.com/powershell/module/exchange/get-autosensitivitylabelpolicy)
- [New-AutoSensitivityLabelPolicy](https://docs.microsoft.com/powershell/module/exchange/new-autosensitivitylabelpolicy)
- [New-AutoSensitivityLabelRule](https://docs.microsoft.com/powershell/module/exchange/new-autosensitivitylabelrule)
- [Remove-AutoSensitivityLabelPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-autosensitivitylabelpolicy)
- [Remove-AutoSensitivityLabelRule](https://docs.microsoft.com/powershell/module/exchange/remove-autosensitivitylabelrule)
- [Set-AutoSensitivityLabelPolicy](https://docs.microsoft.com/powershell/module/exchange/set-autosensitivitylabelpolicy)
- [Set-AutoSensitivityLabelRule](https://docs.microsoft.com/powershell/module/exchange/set-autosensitivitylabelrule)

