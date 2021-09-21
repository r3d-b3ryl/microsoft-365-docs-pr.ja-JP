---
title: Microsoft 365 で秘密度ラベルをコンテンツに自動的に適用する
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
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: 秘密度ラベルを作成する場合、ファイルまたはメールにラベルを自動的に割り当てるか、あるいは推奨するラベルを選択するようにユーザーに求めることができます。
ms.openlocfilehash: 65926c72dfd61cc7a610f547d6c9a9d5fa04451e
ms.sourcegitcommit: 3ec80aba8d5d9acf42ed9b9bf8817c2ec4ab6764
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2021
ms.locfileid: "59456295"
---
# <a name="apply-a-sensitivity-label-to-content-automatically"></a>秘密度ラベルをコンテンツに自動的に適用する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

> [!NOTE]
> Azure Purview (プレビュー) での秘密度ラベルの自動適用の詳細については、「[Azure Purview のコンテンツに自動的にラベルを付ける](/azure/purview/create-sensitivity-label)」を参照してください。

秘密度ラベルを作成する場合、指定した条件に一致したときに、そのラベルをファイルやメールに自動的に割り当てることができます。

秘密度ラベルを自動的にコンテンツに適用する機能が重要である理由は次のとおりです。

- それぞれの分類をいつ使用するかについて、ユーザーをトレーニングする必要がなくなる。

- ユーザーへの依存は、一部のコンテンツを正しく分類するためにのみ必要。

- ユーザーはポリシーについて把握する必要がなくなり、自分たちの仕事に集中できます。

コンテンツが手動でラベル付けされている場合、そのラベルが自動ラベル付けで置き換えられることはありません。 ただし、自動ラベル付けは、自動的に適用された[優先度が低いラベル](sensitivity-labels.md#label-priority-order-matters)を置き換えることができます。

Microsoft 365 でコンテンツに秘密度ラベルを自動的に適用するには、次の 2 つの方法があります。

- **ユーザーがドキュメントを編集したり、メールを作成 (返信または転送) するときのクライアント側のラベル付け**: ファイルやメール (Word、Excel、PowerPoint、Outlook を含む) の自動ラベル付け用に構成されたラベルを使用します。

    この方法は、ユーザーへのラベルの推奨と、ラベルの自動適用をサポートしています。 ただし、どちらの場合も、ユーザーはラベルを承諾または拒否するかどうかを決定し、コンテンツの正しいラベル付けを行います。 このクライアント側のラベル付けでは、ドキュメントを保存する前であってもラベルを適用できるため、ドキュメントの遅延が最小限に抑えられます。 ただし、すべてのクライアント アプリが自動ラベル付けをサポートしているわけではありません。 この機能は、Azure Information Protection 統合ラベル付けクライアント、および [Office の一部のバージョン](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)でサポートされています。

    構成手順については、このページの「[Office アプリの自動ラベル付けを構成する方法](#how-to-configure-auto-labeling-for-office-apps)」を参照してください。

- **コンテンツが既に保存されている (SharePoint または OneDrive で) またはメールで送信された (Exchange Online によって処理される) サービス側のラベル付け**: 自動ラベル付けポリシーを使用します。
    
    この方法は、保存データ (SharePoint および OneDrive のドキュメント) や転送中のデータ (Exchange によって送信または受信されたメール) の自動ラベル付けと呼ばれることもあります。Exchangeの場合、保存中の電子メール (メールボックス) は含まれません。
    
    このラベル付けはアプリケーションではなくサービスによって適用されるため、ユーザーが使用しているアプリやバージョンを気にする必要はありません。 その結果、この機能は、組織全体ですぐに使用できるようになります。また、規模に応じたラベル付けに適しています。 自動ラベル付けポリシーでは、ユーザーがラベル付けプロセスを操作しないので、推奨されるラベル付けをサポートしていません。 代わりに、管理者は、実際にラベルを適用する前に、コンテンツの正しいラベル付けを行うために、シミュレーション モードでポリシーを実行します。

    構成手順については、このページの「[SharePoint、OneDrive、Exchange の自動ラベル付けポリシーを構成する方法](#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)」を参照してください。
    
    SharePoint と OneDrive の自動ラベル付けに固有:
    
    - Word (.docx)、PowerPoint (.pptx)、Excel (.xlsx) の Office ファイルがサポートされています。
        - これらのファイルは、自動ラベル付けポリシーが作成される前または後に、保存時に自動ラベル付けできます。 開いているセッションの一部である (ファイルが開いている) 場合、ファイルに自動ラベル付けはできません。
        - 現在、リスト アイテムへの添付はサポートされておらず、自動ラベル付けされません。
    - テナント内で 1 日あたり最大 25,000 個の自動的にラベル付けされたファイル。
    - テナントあたり最大 100 個の自動ラベル付けポリシーが作成されます。個別に指定した場合、各ポリシーは、最大 100 サイト (SharePoint サイトまたは OneDrive サイト) を対象としています。 すべてのサイトを指定することもできます。この構成は最大 100 サイトから除外されます。
    - シミュレーション モードの場合、およびラベルが適用される場合、自動ラベル付けポリシーの結果として、変更、変更者、変更日の既存の値は変更されません。
    - ラベルが暗号化を適用する場合、[Rights Management 発行者と Rights Management 所有者](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) は、ファイルを最後に変更したアカウントです。

    Exchange の自動ラベル付けに固有:
    
    - 手動でのラベル付けや Office アプリを使用した自動ラベル付けとは異なり、PDF の添付ファイルと Office の添付ファイルも自動ラベル付けポリシーで指定した条件に合わせてスキャンされます。一致するものがある場合、メールにはラベルが付けられますが、添付ファイルにはラベルが付けられません。
        - PDF ファイルの場合、ラベルに暗号化が適用されていると、テナントで [PDF 添付ファイルが有効になっている](ome-faq.yml#are-pdf-file-attachments-supported-)ときにこれらのファイルが暗号化されます。
        - これらの Office ファイルでは、Word (.docx)、PowerPoint (.pptx)、Excel (.xlsx) がサポートされています。 ラベルで暗号化が適用される場合、これらのファイルは暗号化されます。
    - IRM 暗号化を適用する Exchange メール フロー ルールまたはデータ損失防止 (DLP) ポリシーがある場合: これらのルールやポリシーおよび自動ラベル付けポリシーによってコンテンツが識別されると、ラベルが適用されます。 このラベルが暗号化を適用すると、Exchange メール フロー ルールまたは DLP ポリシーの IRM 設定は無視されます。 ただし、そのラベルが暗号化を適用しない場合、メール フロー ルールまたは DLP ポリシーの IRM 設定がラベルに加えて適用されます。
    - ラベルが表示されない IRM 暗号化を使用しているメールは、自動ラベル付けを使用すると一致する場合は、暗号化設定のあるラベルに置き換えられます。
    - 自動ラベル付け条件と一致すると、受信メールに以下のようにラベルが付けられます。
    - ラベルが[暗号化](encryption-sensitivity-labels.md)用に構成されている場合、その暗号化は適用されません。
    - ラベルが[動的マーキング](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)を適用するように構成されている場合、これにより組織外の人の名前が表示される可能性があることに注意してください。
    - ラベルが暗号化を適用する場合、[Rights Management 発行者と Rights Management 所有者](/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner) は、メールを送信するユーザーです。 現在、自動的に暗号化されるすべての受信メール メッセージに Rights Manager 所有者を設定する方法はありません。

## <a name="compare-auto-labeling-for-office-apps-with-auto-labeling-policies"></a>Office アプリの自動ラベル付けと自動ラベル付けポリシーを比較する

次の表は、2 つの相補的な自動ラベル付け方法の違いを特定するのに役立ちます。

|機能または動作|ラベル設定: ファイルやメールの自動ラベル付け  |ポリシー: 自動ラベル付け|
|:-----|:-----|:-----|
|アプリの依存関係|はい ([最小バージョン](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)) |いいえ \* |
|場所による制限|いいえ |はい |
|条件: カスタムの機密情報の種類に関する Exact Data Match|はい |いいえ |
|条件: トレーニング可能な分類子|はい |いいえ |
|条件: メールの共有オプションと追加オプション|いいえ |はい |
|条件: 例外|いいえ |はい (メールのみ) |
|推奨事項、ポリシーのヒント、ユーザー上書き|はい |いいえ |
|シミュレーション モード|いいえ |はい |
|条件についてチェックされた Exchange 添付ファイル|いいえ | はい|
|視覚的なマーキングの適用 |はい |はい (メール専用) |
|ラベルなしで適用された IRM 暗号化の上書き|はい (ユーザーがエクスポートの最小使用権を持っている場合) |はい (メール専用) |
|受信メールのラベル付け|いいえ |はい|

\* 自動ラベル付けは、現在、一部の地域では利用できません。 テナントがこの機能をサポートできない場合、**自動ラベル付け** タブはコンプライアンス センターに表示されません。

## <a name="how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label"></a>複数のラベルに適用するときの複数の条件の評価方法

ラベルは、ポリシー内で指定した位置に従って評価の順序を決められます。先頭に配置したラベルが最下位 (機密性が最も低い) になり、最後に配置したラベルが最上位 (機密性が最も高い) になります。優先度に関する詳細については、「[ラベルの優先度 (順序の問題)](sensitivity-labels.md#label-priority-order-matters)」を参照してください。

## <a name="dont-configure-a-parent-label-to-be-applied-automatically-or-recommended"></a>自動適用または推奨されるように親ラベルを構成しない

親ラベル (サブラベルのあるラベル) はコンテンツに適用できません。 Office アプリで親ラベルが自動適用または自動推奨されるように構成されていないこと、自動ラベル ポリシーで親ラベルが選択されていないことを確認してください。 その場合、親ラベルをコンテンツに適用できなくなる可能性があります。

自動ラベルでサブラベルも使用するには、必ず親ラベルとサブラベルの両方を発行してください。

親ラベルとサブラベルの詳細については、「[サブラベル (ラベルのグループ化)](sensitivity-labels.md#sublabels-grouping-labels)」を参照してください。

## <a name="how-to-configure-auto-labeling-for-office-apps"></a>Office アプリの自動ラベル付けを構成する方法

Office アプリの組み込みラベル付けについては、Office アプリでの自動ラベル付けに[必要な最小バージョン](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)を確認してください。

Azure Information Protection 統合ラベル付けクライアントは、組み込みおよびカスタムの機密情報の種類に対する自動ラベル付けをサポートしていますが、完全データ一致 (EDM) を使用するトレーニング可能な分類子や機密情報の種類には対応していません。

Office アプリの自動ラベル付け設定は、[機密ラベルを作成または編集する](create-sensitivity-labels.md)ときに使用できます。 ラベルのスコープとして **[ファイルとメール]** が選択されていることを確認してください。

![ファイルとメールの秘密度ラベルの範囲オプション](../media/filesandemails-scope-options-sensitivity-label.png)

構成内を移動すると、**[ファイルやメールの自動ラベル付け]** ページが表示されます。このページでは、機密情報の種類またはトレーニング可能な分類子の一覧から選択できます。

![Office アプリでの自動ラベル付けのラベル条件](../media/sensitivity-labels-conditions.png)

この秘密度ラベルが自動的に適用されると、ユーザーの Office アプリに通知が表示されます。以下のような例があります:

![ドキュメントにラベルが自動適用されたという通知](../media/sensitivity-labels-msg-doc-was-auto-labeled.PNG)

### <a name="configuring-sensitive-info-types-for-a-label"></a>ラベルの機密情報の種類の構成

**機密情報の種類** オプションを選択すると、データ損失防止 (DLP) ポリシーを作成するときと同じ機密情報の種類の一覧が表示されます。 そのため、たとえば、クレジットカード番号、社会保障番号、またはパスポート番号など、お客様の個人情報を含むコンテンツに極秘ラベルを自動的に適用できます。

![Office アプリの自動ラベル付け用の機密情報の種類](../media/sensitivity-labels-sensitive-info-types.png)

DLP ポリシーを構成する場合と同様に、インスタンス数と一致精度を変更することで条件を調整できます。以下のような例があります:

![一致精度とインスタンス数のオプション](../media/sit-confidence-level.png)

これらの構成オプションの詳細については、DLP ドキュメント「[一致の難易度を上下するためにルールを調整する](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)」を参照してください。

また、DLP ポリシー構成と同様に、条件で検知する必要があるのは、機密情報の種類のすべてか、またはそのうちの 1 つだけかを選択できます。 また、条件をより柔軟または複雑にするには、[グループを追加し、グループ間で論理演算子を使用](data-loss-prevention-policies.md)できます。

> [!NOTE]
> カスタムの機密情報の種類に基づく自動ラベル付けは、OneDrive および SharePoint で新しく作成または変更されたコンテンツにのみ適用されます。既存のコンテンツには適用されません。この制限は、自動ラベル付けポリシーにも適用されます。

#### <a name="custom-sensitive-information-types-with-exact-data-match"></a>Exact Data Match によるカスタムの機密情報の種類

秘密度ラベルは、カスタムの機密情報の種類に [Exact Data Match (EDM) ベースの分類](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) を使用するように構成できます。 ただし、現時点では、EDM を使用しない機密情報の種類を少なくとも 1 つ指定する必要があります。 たとえば、**クレジット カード番号** など、組み込みの機密情報の種類のうちの 1 つ。

機密情報の種類の条件に対して EDM のみを使用して秘密度ラベルを構成した場合、ラベルの自動ラベル付け設定は自動的にオフになります。

### <a name="configuring-trainable-classifiers-for-a-label"></a>ラベルのトレーニング可能な分類子を構成する

このオプションを使用する場合は、自動ラベル付け用に構成された少なくとも 1 つの他の秘密度ラベルと[機密情報の種類のオプション](#configuring-sensitive-info-types-for-a-label)をテナントに公開していることを確認してください。

**トレーニング可能な分類子** のオプションを選択する場合、Microsoft から 1 つ以上のトレーニング可能な組み込み分類子を選択します。 独自のトレーニング可能なカスタム分類子を作成している場合は、以下を選択できます。

![トレーニング可能な分類子と秘密度ラベルのオプション](../media/sensitivity-labels-classifers.png)

これらの分類子の詳細については、「[トレーニング可能な分類子 (プレビュー) の詳細](classifier-learn-about.md)」を参照してください。

### <a name="recommend-that-the-user-applies-a-sensitivity-label"></a>ユーザーが秘密度ラベルを適用することを推奨

必要に応じて、ラベルを適用することをユーザーに推奨できます。このオプションでは、分類および関連する保護を受け入れるか、またはラベルがそのコンテンツに適していない場合、推奨事項を無視するかをユーザーが選択できます。

![秘密度ラベルをユーザーに推奨するためのオプション](../media/Sensitivity-labels-Recommended-label-option.png)

ラベルを推奨される操作として適用するように条件を構成したときの、Azure Information Protection の統合ラベル付けクライアントからのプロンプトの例を、カスタム ポリシー ヒントと共に示します。ポリシー ヒントに表示するテキストを選択できます。

![推奨ラベルを適用するためのプロンプト](../media/Sensitivity-label-Prompt-for-required-label.png)

### <a name="when-automatic-or-recommended-labels-are-applied"></a>自動ラベルまたは推奨ラベルが適用されている場合

Office アプリでの自動ラベル付けと推奨ラベル付けの実装は、Office に組み込まれているラベル付けを使用しているか、または Azure Information Protection の統合ラベル付けクライアントを使用しているかによって異なります。ただし、どちらの場合も、次のようになります。

- 以前に手動でラベル付けされた、または以前に高い秘密度で自動的にラベル付けされたドキュメントや電子メールに自動ラベル付けを使用することはできません。(単一の保持ラベルに加えて) ドキュメントまたは電子メールに適用できる機密ラベルは 1 つだけであることにご注意ください。

- 以前に高い感度でラベル付けされたドキュメントまたはメールに推奨されるラベル付けを使用することはできません。 コンテンツがすでに高い感度でラベル付けされている場合、ユーザーには推奨事項とポリシーのヒントが記載されたプロンプトは表示されません。

組み込みのラベル付けに関してのみ以下の点が当てはまります。

- 必ずしもすべての Office アプリで自動 (および推奨) ラベル付けがサポートされるわけではありません。 詳しくは、「[アプリでの秘密度ラベル機能のサポート](sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)」を参照してください。

- Word のデスクトップ バージョンにおける推奨ラベルでは、推奨をトリガーした機密コンテンツにフラグが付けられるので、ユーザーが確認して、推奨されている秘密度ラベルを適用しないで機密コンテンツを削除できます。

- こうしたラベルが Office アプリで適用される方法、スクリーンショット例、機密情報の検出方法について詳しくは、「[Office のファイルとメールに秘密度ラベルを自動的に適用、または推奨する](https://support.microsoft.com/office/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)」を参照してください。

Azure Information Protection 統合ラベル付けクライアントに関してのみ以下の点が当てはまります。

- 自動ラベル付けと推奨ラベル付けは、Word、Excel、PowerPoint でドキュメントが保存されるときと、Outlook でメールが送信されるときに適用されます。

- Outlook で推奨ラベル付けをサポートするには、最初に[詳細なポリシー設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#enable-recommended-classification-in-outlook)を構成する必要があります。

- ドキュメントやメール内の本文、およびヘッダーとフッターに含まれる機密情報が検出されますが、件名やメールの添付ファイルのものは検知されません。

## <a name="how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange"></a>SharePoint、OneDrive、Exchange の自動ラベル付けポリシーを構成する方法

自動ラベル付けポリシーを構成する前に、前提条件を必ずご確認ください。

### <a name="prerequisites-for-auto-labeling-policies"></a>自動ラベル付けポリシーの前提条件

- シミュレーション モード:
  - Microsoft 365 の監査を有効にする必要があります。 監査を有効にする必要がある場合、または監査が既に有効になっているかどうかが不明の場合は、「[監査ログの検索を有効または無効にする](turn-audit-log-search-on-or-off.md)」を参照してください。
  - ソース ビューでファイルやメールの内容を表示するには、**コンテンツ エクスプローラーのコンテンツ閲覧者** の役割が必要です。 既定では、全体管理者にはこの役割はありません。 このアクセス許可がない場合、[**一致したアイテム**] タブからアイテムを選択してもプレビュー ウィンドウは表示されません。

- SharePoint および OneDrive にあるファイルに自動でラベルを付けるには:
  - [SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にしています](sensitivity-labels-sharepoint-onedrive-files.md)。
  - 自動ラベル付けポリシーの実行時に、別のプロセスまたはユーザーがファイルを開いておくことはできません。 編集用にチェックアウトされたファイルは、このカテゴリに分類されます。

- 組み込みの機密度の種類ではなく、[カスタムの機密情報の種類](sensitive-information-type-learn-about.md)を使用する場合は、次の操作を行います。
  - カスタムの機密情報の種類は、カスタムの機密情報の種類が作成された後に SharePoint または OneDrive で追加または変更されたコンテンツにのみ適用されます。
  - 新しいカスタムの機密情報の種類をテストするには、自動ラベル付けポリシーを作成する前に作成してから、テスト用のサンプル データを使用して新しいドキュメントを作成します。

- 自動ラベル付けポリシー用に選択できる、[作成および公開された](create-sensitivity-labels.md) (少なくとも 1 人のユーザーに対して) 1 つ以上の秘密度ラベル。 これらのラベルの場合:
  - 概要で説明したように、ラベル設定は自動ラベル付けポリシーを補完するため、Office アプリのラベル設定の自動ラベル付けがオンかオフかは関係ありません。
  - 自動ラベル付けに使用するラベルが視覚的なマーキング (ヘッダー、フッター、透かし) を使用するように構成されている場合、これらはドキュメントに適用されないことに注意してください。
  - ラベルが[暗号化](encryption-sensitivity-labels.md)を適用する場合:
    - 自動ラベル付けポリシーに SharePoint または OneDrive の場所が含まれている場合は、[**アクセス許可を今すぐ割り当てる**] 設定でラベルを構成する必要があります。
    - 自動ラベル付けポリシーが Exchange 専用の場合、ラベルは、[**アクセス許可を今すぐ割り当てる**] または [**ユーザーにアクセス許可を割り当てさせる**] ([転送しない] または [暗号化のみ] オプションの場合) のいずれかに構成できます。

### <a name="learn-about-simulation-mode"></a>シミュレーション モードの詳細

シミュレーション モードは、自動ラベル付けポリシーに固有であり、ワークフローに組み込まれています。 ポリシーによって少なくとも 1 つのシミュレーションが実行されるまで、ドキュメントとメールに自動的にラベルを付けることはできません。

自動ラベル付けポリシーのワークフロー:

1. 自動ラベル付けポリシーを作成して構成する。

2. ポリシーをシミュレーション モードで実行します。完了までに 12 時間かかる場合があります。 シミュレーションが完了すると、 [アクティビティ アラート](alert-policies.md)を受信するように構成されたユーザーに送信されるメール通知がトリガーされます。

3. 結果を確認し、必要に応じてポリシーを調整します。 シミュレーション モードを再実行し、シミュレーションが再度完了するまで待機します。

4. 必要に応じて、手順 3 を繰り返します。

5. 実稼働環境に展開する。

シミュレーションされた展開は、PowerShell の WhatIf パラメーターのように動作します。 定義したルールを使用して、自動ラベル付けポリシーが選択したラベルを適用したかのようにレポートされた結果が表示されます。 その後、必要に応じてルールの精度を高め、シミュレーションを再実行できます。 ただし、Exchange の自動ラベル付けは、メールボックスに保存されたメールではなく、送受信されるメールに適用されるため、完全に同じメール メッセージを送受信することができなければ、シミュレーションのメールの結果に一貫性があるとは期待できません。

シミュレーション モードでは、展開前に自動ラベル付けポリシーの範囲を徐々に広げることもできます。 たとえば、1 つのドキュメント ライブラリを持った SharePoint サイトなどの 1 つの場所から始めることができます。 次に、反復的な変更を加えて、範囲を複数のサイトに拡大し、次に OneDrive などの別の場所に拡大します。

最後に、シミュレーション モードを使用して、自動ラベル付けポリシーの実行に必要な時間の概算を提供し、シミュレーション モードを使用せずに実行するタイミングを計画してスケジュールすることができます。

### <a name="creating-an-auto-labeling-policy"></a>自動ラベル付けポリシーの作成

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 コンプライアンス センター</a>で、機密ラベルに移動します。

    - [**ソリューション**]  >  [**Information Protection**]

    このオプションがすぐに表示されない場合は、まず [**すべてを表示**] を選択します。

2. [**自動ラベル付け**] タブを選択します。

    ![自動ラベル付けタブ。](../media/auto-labeling-tab.png)

    > [!NOTE]
    > **[自動ラベル付け]** タブが表示されない場合、この機能は現在お住まいの地域ではご利用いただけません。

3. [**+自動ラベル付けポリシーの作成**] を選択します。 これにより、新しいポリシー構成が開始されます。

    ![自動ラベル付けの新しいポリシー構成。](../media/auto-labeling-wizard.png)

4. [**このラベルを適用する情報を選択する**] ページの場合: [**財務**] または [**プライバシー**] などのテンプレートのいずれかを選択します。 ドロップダウンの **表示オプション** を使用して、検索を絞り込むことができます。 または、テンプレートが要件を満たしていない場合は、[**カスタム ポリシー**] を選択します。 **[次へ]** を選択します。

5. [**自動ラベル ポリシーに名前を付ける**] ページの場合: 一意の名前を入力し、必要に応じて説明を入力して、自動的に適用されるラベル、場所、ラベル付けするコンテンツを識別する条件を識別します。

6. [**ラベルを適用する場所を選択する**] ページの場合: Exchange、SharePoint、OneDrive の場所を選択して指定します。 選択した場所の既定値を [**すべて**] のままにしたくない場合は、リンクを選択して特定のインスタンスを選択します。 [**次へ**] を選択します。

    ![自動ラベル付け構成の [場所の選択] ページ。](../media/locations-auto-labeling-wizard.png)
    
    個々の OneDrive アカウントを指定するには、「[組織内のすべてのユーザーの OneDrive の URL 一覧を取得する](/onedrive/list-onedrive-urls)」を参照してください。

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
    - ヘッダーがパターンと一致している
    - 件名がパターンと一致している
    - 受信者のアドレスに単語が含まれている
    - 受信者のアドレスがパターンと一致している
    - 送信者のアドレスがパターンと一致している
    - 送信者のドメインが次の場合
    - 受信者が次のメンバーの場合
    - 送信者が

    これらの条件ごとに、例外を指定できます。

8. 以前の選択に応じて、条件と例外を使用して新しいルールを作成する機会があります。

    機密情報の種類の構成オプションは、Office アプリの自動ラベル付けに選択したものと同じです。 詳細情報が必要な場合は、「[ラベルの機密情報の種類の構成](#configuring-sensitive-info-types-for-a-label)」を参照してください。

    必要なすべてのルールを定義し、状態が [オン] になっていることを確認したら、[**次へ**] を選択して、自動適用するラベルの選択に進みます。

9. [**自動適用するラベルを選択する**] ページの場合: [**+ ラベルの選択**] を選択し、[**機密ラベルの選択**] ウィンドウのラベルを選択し、[**次へ**] を選択します。

10. **[ポリシーを今すぐテストするか後でテストするかを決定する]** ページの場合: シミュレーション モードで、今すぐ自動ラベル付けポリシーを実行する準備が整っている場合は、**[シミュレーション モードでポリシーを実行する]** を選択します。 それ以外の場合は、**[ポリシーをオフのままにする]** を選択します。 [**次へ**] を選択します。

    ![構成済みの自動ラベル付けポリシーをテストします。](../media/simulation-mode-auto-labeling-wizard.png)

11. **[概要]** ページの場合: 自動ラベル付けポリシーの構成を確認し、必要な変更を行い、構成を完了します。

**[情報保護]** > **[自動ラベル付け]** ページでは、自動ラベル付けポリシーを **[シミュレーション]** または **[オフ]** セクションのどちらかで確認できます。これは、シミュレーション モードで実行することを選択したかどうかによって決まります。 ポリシーを選択して、構成と状態の詳細 (**[ポリシー シミュレーションの実行中]** など) を確認します。 シミュレーション モードのポリシーの場合は、**[一致したアイテム]** タブを選択して、指定したルールに一致した電子メールまたはドキュメントを確認します。

このインターフェイスからは、次のようにポリシーを直接変更できます。

- **[オフ]** セクションのポリシーの場合は、**[ポリシーの編集]** ボタンを選択します。

- **[シミュレーション]** セクションのポリシーの場合は、いずれかのタブからページの上部にある **[ポリシーの編集]** オプションを選択します。

    ![自動ラベル付けポリシーの編集オプション。](../media/auto-labeling-edit.png)

    シミュレーションなしでポリシーを実行する準備が整っているときには、**[ポリシーを有効にする]** オプションを選択します。

自動ポリシーは、削除されるまで継続的に実行されます。 たとえば、新しいドキュメントや変更されたドキュメントは、現在のポリシー設定に含まれます。

また、適切な[アクセス許可](data-classification-content-explorer.md#permissions)がある場合は、[コンテンツ エクスプローラー](data-classification-content-explorer.md)を使用して、自動ラベル付けポリシーの結果を確認することもできます。

- **コンテンツ エクスプローラーのリスト閲覧者** では、ファイルのラベルは表示できますが、ファイルのコンテンツは表示できません。
- **コンテンツ エクスプローラーのコンテンツ閲覧者** では、ファイルの内容を表示できます。

> [!TIP]
> コンテンツ エクスプローラーを使用して、機密情報を含むラベルの付いていないドキュメントがある場所を特定することもできます。 この情報を使用して、自動ラベル付けポリシーにこれらの場所を追加することを検討し、識別された機密情報の種類をルールとして含めます。

### <a name="use-powershell-for-auto-labeling-policies"></a>自動ラベル付けポリシーに PowerShell を使用する

[セキュリティ/コンプライアンス センターの PowerShell](/powershell/exchange/scc-powershell) を使用して、自動ラベル付けポリシーを作成し、構成できます。 これにより、自動ラベル付けポリシーの作成やメンテナンスを完全にスクリプト化できるようになり、OneDrive や SharePoint の場所に複数の URL を指定する効率的な方法も提供できます。

PowerShell でコマンドを実行する前に、最初に[セキュリティ/コンプライアンス センターの PowerShell に接続](/powershell/exchange/connect-to-scc-powershell)する必要があります。

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

- [Get-AutoSensitivityLabelPolicy](/powershell/module/exchange/get-autosensitivitylabelpolicy)
- [New-AutoSensitivityLabelPolicy](/powershell/module/exchange/new-autosensitivitylabelpolicy)
- [New-AutoSensitivityLabelRule](/powershell/module/exchange/new-autosensitivitylabelrule)
- [Remove-AutoSensitivityLabelPolicy](/powershell/module/exchange/remove-autosensitivitylabelpolicy)
- [Remove-AutoSensitivityLabelRule](/powershell/module/exchange/remove-autosensitivitylabelrule)
- [Set-AutoSensitivityLabelPolicy](/powershell/module/exchange/set-autosensitivitylabelpolicy)
- [Set-AutoSensitivityLabelRule](/powershell/module/exchange/set-autosensitivitylabelrule)

## <a name="recent-enhancements-for-auto-labeling-policies"></a>自動ラベル付けポリシーの最近の機能強化

OneDrive と SharePoint の自動ラベル付けポリシーの最近の機能強化では、以前のバージョンと比較して、次の機能強化が含まれています:

- テナントあたり最大 100 個の自動ラベル付けポリシー。(以前は最大 10 個)

- すべての OneDrive サイトと SharePoint サイト (新しいポリシーの既定値) のサポートと、これまでのように URL で各サイトを入力することなしに使用可能な SharePoint サイトを選択する機能。 新しい既定値である **All** を使用すると、テナント内のすべての既存の SharePoint サイトと OneDrive アカウント、および新しく作成されたすべてのサイトとアカウントがポリシーに自動的に含められます。 SharePoint の **サイトの選択** を選択しても、必要に応じて URL でサイトを手動で入力できます。

- 自動ラベル付けポリシーで個々のサイトを指定すると、従来のように 10 サイトではなく最大 100 サイトがサポートされるようになりました。

- 自動ラベル付けポリシーあたり最大 1,000,000 個の一致ファイルが使えますが、1 日あたりテナント内で自動的にラベル付けされるファイルは今までどおり合計 25,000 個です。

- シミュレーションの改善
  - シミュレーション モードで自動ラベル付けポリシーを実行すると、最大 48 時間以内ではなく 12 時間以内に完了します。
  - 一致するすべてのアイテムではなく、各サイト (OneDrive または SharePoint) のレビュー用に最大 100 個のランダムにサンプリングされた一致ファイルを提供することで、パフォーマンスが向上します。
  - シミュレーションが完了すると、 [アクティビティ アラート](alert-policies.md)を受信するように構成されたユーザーにメール通知が送信されます。

- 一致したアイテムを確認するのに役立つ機能強化:
  - サンプリングされた一致項目の追加メタデータ情報。
  - SharePoint サイト名やファイル所有者など、一致するアイテムに関する情報をエクスポートする機能。 この情報を使用して、一致したファイルをピボットして分析し、必要に応じてファイル所有者に委任して確認してもらうことができます。

> [!TIP]
> サポートされるポリシーとサイトの数を増やすには、PowerShell を使用して新しいポリシーを効率的に作成し、既存のポリシーにサイトを追加します。 詳細については、このページの「[PowerShell を使用した自動ラベル付けポリシー](#use-powershell-for-auto-labeling-policies)」のセクションを参照してください。

### <a name="how-to-determine-whether-your-tenant-has-the-new-enhancements"></a>テナントに新しい拡張機能があるかどうかを確認する方法

テナントに新しい拡張機能が追加されると、**[自動ラベル付け]** タブに次の通知が表示されるようになります:

![テナントに新しい拡張機能があることを確認するバナー](../media/auto-labeling-updatedbanner.png)

> [!NOTE]
> テナントが新しい拡張機能を受け取ったときに、シミュレーション モードだった自動ラベル付けポリシーがある場合は、シミュレーションを再実行する必要があります。 このシナリオが当てはまる場合は、シミュレーションを確認するときに、**シミュレーションの再起動** を選択するように求められます。 シミュレーションを再起動しない場合、シミュレーションは完了しません。
>
> ただし、機能強化は、シミュレーションなしで実行されているすべての自動ラベル付けポリシーと、作成するすべての新しい自動ラベル付けポリシーに引き続き適用されます。

## <a name="tips-to-increase-labeling-reach"></a>ラベル付けの範囲を拡大するためのヒント

自動ラベル付けは、組織が所有する Office ファイルを分類、ラベル付け、および保護するための最も効率的な方法の 1 つですが、ラベル付けの範囲を拡大するための追加の方法のいずれかで補足できるかどうかを確認してください。

- [Azure Information Protection 統合ラベル付けクライアント](/azure/information-protection/rms-client/aip-clientv2)を使用する場合:

  - ネットワーク共有や SharePoint Server ライブラリなどのオンプレミス データ ストア内のファイルの場合: [スキャナー](/azure/information-protection/deploy-aip-scanner)を使用して、これらのファイル内の機密情報を検出し、適切にラベル付けします。 これらのファイルを Microsoft 365 の SharePoint に移行またはアップロードすることを計画している場合は、スキャナーを使用して、ファイルをクラウドに移動する前に、ファイルにラベル付けします。

  - 秘密度ラベルを使用する前に別のラベル付けソリューションを使用した場合: PowerShell と[詳細設定を使用して、これらのソリューションのラベルを再利用します](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#migrate-labels-from-secure-islands-and-other-labeling-solutions)。

- どの秘密度ラベルを適用するかをユーザーにトレーニングした後、[手動ラベル付け](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)を行います。 適用すべきラベルをユーザーが理解していると確信できる場合は、[ポリシー設定](sensitivity-labels.md#what-label-policies-can-do)として既定のラベルと必須のラベルを構成することを検討してください。

さらに、SharePoint で[新しいファイルを既定で機密としてマーク](/sharepoint/sensitive-by-default)して、少なくとも 1 つの DLP ポリシーがファイルのコンテンツをスキャンするまでゲストが新しく追加されたファイルにアクセスできないようにすることを検討してください。
