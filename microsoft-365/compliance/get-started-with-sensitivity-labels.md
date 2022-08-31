---
title: 秘密度ラベルの使用を開始する
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 管理者、ライセンス要件、および機密ラベルを使用して組織のデータを保護する一般的なシナリオの規範的な手順。
ms.openlocfilehash: 2a82a788ae766050c663d3d35332470aa48d9a20
ms.sourcegitcommit: 57c2f5ba74e238543d6fd724ed79527547bd0780
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2022
ms.locfileid: "67069649"
---
# <a name="get-started-with-sensitivity-labels"></a>秘密度ラベルの使用を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

秘密度ラベルの概要とそれらが組織のデータを保護する方法の詳細については、「[秘密度ラベルの詳細](sensitivity-labels.md)」を参照してください。

[Azure Information Protection](/azure/information-protection/what-is-information-protection) を使用していて、Azure ポータルから管理されている Azure Information Protection ラベルを引き続き使用している場合は、これらのラベルを[統合ラベル付けプラットフォーム](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)に移行する必要があります。 Windows コンピューターの場合、公開された機密ラベルに[使用するラベル付けクライアント](/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)を選択できます。

秘密度ラベルを使用して組織のデータを保護する準備ができたら、次の手順に従います。

1. **ラベルを作成する。** コンテンツのさまざまなレベルに対する組織の分類方法に従って、秘密度ラベルを作成して名前を付けます。 ユーザーにとって意味のある、一般的な名前または用語を使用します。 分類方法がまだ確率していない場合は、「個人用」、「パブリック」、「一般」、「社外秘」、および「極秘」などのラベル名を使って使用開始することを検討してください。 サブラベルを使用すると、類似したラベルをカテゴリ別にグループ化できます。 ラベルを作成するときは、ユーザーが適切なラベルを選択できるよう、ツールヒントのテキストを使用します。
    
    分類法を定義するためのより広範なガイダンスについては、[Service Trust Portal](https://aka.ms/DataClassificationWhitepaper) のホワイト ペーパー「データ分類と秘密度ラベルの分類」をダウンロードしてください。

2. **各ラベルの機能を定義する。** 各ラベルに関連付ける必要がある保護設定を構成します。 たとえば、"一般" ラベルなどの秘密度の低いコンテンツには単にヘッダーやフッターを適用し、"社外秘" ラベルなどの秘密度のより高いコンテンツには透かしや暗号化を適用する、といったことができます。

3. **ラベルを発行する。** 秘密度ラベルの構成が完了したら、ラベル ポリシーを使用してラベルを公開します。 ラベルを使用する必要があるユーザーとグループおよび使用するポリシー設定を決定します。 1 つのラベルは再利用できます。 一度定義したラベルは、異なるユーザーに割り当てる複数のラベル ポリシーに含めることができます。 たとえば、ラベル ポリシーをごく少数のユーザーに対して適用して、秘密度ラベルを試験運用することができます。 組織全体に対してラベルを展開する準備ができたら、ラベルの新しいラベル ポリシーを作成し、今回はすべてのユーザーを指定することができます。

> [!TIP]
> 既定のラベルの自動作成と、手順 1 - 3 の管理を行う既定のラベル ポリシーの対象となる場合があります。 詳細については、「[Microsoft Purview Information Protection の既定のラベルとポリシー](mip-easy-trials.md)」を参照してください。

秘密度ラベルを展開して適用するための基本的な流れ:

![秘密度ラベルのワークフローを示す図。](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>秘密度ラベルのサブスクリプションとライセンスの要件

秘密度ラベルはさまざまな異なるサブスクリプションに対応しており、ユーザーのライセンス要件は使用する機能によって異なります。

Microsoft Purview 機能のメリットを得られるようにユーザーにライセンスを付与するためのオプションを確認するには、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)」を参照してください。 秘密度ラベルについては、「[Microsoft Purview Information Protection: 秘密度ラベル付け](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-information-protection-sensitivity-labeling)」のセクションおよび機能レベルのライセンス要件に関する [PDF ダウンロード](https://go.microsoft.com/fwlink/?linkid=2139145) ファイルを参照してください。

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>機密ラベルの作成と管理に必要なアクセス許可

秘密度ラベルを作成するコンプライアンス チームのメンバーには、Microsoft Purview コンプライアンス ポータルへのアクセス許可が必要です。

既定では、テナントのグローバル管理者はこの管理センターへのアクセス権を所有し、コンプライアンス責任者や他のユーザーにアクセス権を付与できます (テナント管理者が持つすべての権限を付与する必要はありません)。この委任された制限付き管理者アクセス許可については、ユーザーを **[コンプライアンス データ管理者]**、**[コンプライアンス管理者]**、または **[セキュリティ管理者]** 役割グループに追加します。 

既定の役割を使用する代わりに、新しい役割グループを作成し、 **秘密度ラベル管理者** または **組織の構成** の役割をこのグループに追加することもできます。読み取り専用の役割の場合は、**秘密度ラベル リーダー** を使用します。 

> [!NOTE]
> プレビュー段階では、次の役割グループを使用できます。
> - **情報保護**
> - **Information Protection 管理者**
> - **Information Protection アナリスト**
> - **Information Protection 調査担当者**
> - **Information Protection 閲覧者**
>
> それぞれの役割とその役割に含まれる新しい役割の説明については、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">[Microsoft Purview コンプライアンス ポータル]</a> > **[アクセス許可と役割]** > **[コンプライアンス センター]** > **[役割]** で役割グループを選択し、次にポップアップ ウィンドウで説明を確認します。または、「[セキュリティ/コンプライアンス センターの役割グループ](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center)」を参照してください。

ユーザーを既定のロール、グループ、役割に追加する手順、または独自の役割グループを作成する手順については、「[Microsoft Purview コンプライアンス ポータルのアクセス許可](microsoft-365-compliance-center-permissions.md)」を参照してください。

これらのアクセス許可は、機密ラベルとそのラベル ポリシーの作成と構成を行う場合にのみ必要です。 アプリまたはサービスでラベルを適用するためには必要はありません。 秘密度ラベルに関連する特定の構成に追加のアクセス許可が必要な場合、それらのアクセス許可はそれぞれのドキュメントの説明に記載されています。

## <a name="deployment-strategy-for-sensitivity-labels"></a>秘密度ラベルの展開戦略
組織の秘密度ラベルの展開戦略を成功させるには、ビジネス要件と技術要件、概念実証テスト、内部チェックポイントと承認、運用環境の最終的な展開を特定し管理する作業仮想チームを作成します。

次のセクションの表を使用して、最も影響力のあるビジネス要件にマッピングされる上位 1 つまたは 2 つのシナリオを特定することをお勧めします。 これらのシナリオが展開されたら、リストに戻り、次に展開する優先順位の 1 つまたは 2 つを特定します。

## <a name="common-scenarios-for-sensitivity-labels"></a>秘密度ラベルの一般的なシナリオ

すべてのシナリオで、[秘密度ラベルとそのポリシーを作成して構成する](create-sensitivity-labels.md)必要があります。

|必要な作業...|ドキュメント|
|----------------|---------------|
|Office アプリの秘密度ラベルを管理して、コンテンツの作成時にラベルを付けられるようにする (すべてのプラットフォームでの手動によるラベル付けのサポートを含む) |[Office アプリの秘密度ラベルを管理する](sensitivity-labels-office-apps.md)|
|Windows 上の Office アプリの追加機能で (必要な場合)、ラベル付けをエクスプローラーと PowerShell に拡張する|[Windows 用のAzure Information Protection 統合ラベル付けクライアント](/azure/information-protection/rms-client/aip-clientv2)|
|秘密度ラベルを使用してドキュメントやメールを暗号化し、そのコンテンツにアクセスできるユーザーとその使用方法を制限する |[秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する](encryption-sensitivity-labels.md)|
|ドキュメントが暗号化されている場合でも、共同編集、電子情報開示、データ損失防止、検索をサポートし、Office on the web の秘密度ラベルを有効にする | [SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md)
|既定の秘密度ラベルで自動的にラベル付けする SharePoint 内のファイル | [SharePoint ドキュメント ライブラリの既定の秘密度ラベルを構成する](sensitivity-labels-sharepoint-default-label.md)
|ドキュメントが暗号化されている場合に、Office デスクトップ アプリで共同編集と自動保存を使用する | [機密度ラベルを使用して暗号化されたファイルの共同編集を有効にする](sensitivity-labels-coauthoring.md)
|秘密度ラベルをドキュメントとメールに自動的に適用する | [機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)|
|秘密度ラベルを使用して、Teams や SharePoint のコンテンツを保護する |[Microsoft Teams、Microsoft 365 グループ、SharePoint サイトで秘密度ラベルを使用する](sensitivity-labels-teams-groups-sites.md)|
|秘密度ラベルを使用して、SharePoint と OneDrive のサイトと個々のドキュメントの既定の共有リンクの種類を構成する |[秘密度ラベルを使用して、SharePoint と OneDrive のサイトとドキュメントの既定の共有リンクを設定する](sensitivity-labels-default-sharing-link.md)|
|ドキュメント理解モデルに機密ラベルを適用すると、SharePoint ライブラリ内の識別されたドキュメントが自動的に分類および保護されます |[Microsoft SharePoint Syntex のモデルに秘密度ラベルを適用する](/microsoft-365/contentunderstanding/apply-a-sensitivity-label-to-a-model)|
|特定の感度ラベルを持つファイルまたはメールをユーザーが共有しないように、または警告します。 |[DLP ポリシーで秘密度ラベルを条件として使用する](dlp-sensitivity-label-as-condition.md) |
|個人データを含むコンテンツが共有されつつあるか、保護が必要であるというアラートを受け取ったときに、機密ラベルをファイルに適用する| [プライバシー リスク管理のアラートを調査して修復します](/privacy/priva/risk-management-alerts)|
|保持ラベルを適用して、特定の秘密度ラベルを持つファイルまたはメールを保持または削除する|[保持ラベルを自動的に適用してコンテンツを保持または削除する](apply-retention-labels-automatically.md) |
|オンプレミスのデータ ストアに保存されているファイルを検出、ラベル付け、保護する |[ファイルを自動的に分類および保護するための Azure Information Protection スキャナーを展開する](/azure/information-protection/deploy-aip-scanner)|
|クラウドのデータ ストアに保存されているファイルを検出、ラベル付け、保護する|[クラウドに保存されている規制対象および機密データを検出、分類、ラベル付け、保護する](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|ファイルや電子メールに使用しているものと同じ秘密度ラベルを使用して SQL データベース列にラベルを付けて、エクスポート時に、この構造化データを保護し続けることができる統合ラベル付けソリューションを組織が持つようにします。 |[Azure SQL Database、Azure SQL Managed Instance、Azure Synapse Analytics のデータの検出と分類](/azure/azure-sql/database/data-discovery-and-classification-overview) <br /><br /> [SQL Server オンプレミスの SQL データの検出と分類](/sql/relational-databases/security/sql-data-discovery-and-classification)|
|Power BI でラベルの適用と表示をし、サービスの外部に保存されたデータを保護する|[Power BI の秘密度ラベル](/power-bi/admin/service-security-sensitivity-label-overview)|
|組織で秘密度ラベルがどのように使用されているかを監視し、理解する|[データ分類の説明](data-classification-overview.md)|
|秘密度ラベルの適用をサード パーティ製アプリやサービスに拡大する|[Microsoft Information Protection SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|
|Azure Blob Storage、Azure Files、Azure Data Lake Storage、マルチクラウド データ ソースなど、Microsoft Purview データ マップ アセットのコンテンツ全体に秘密度ラベルを拡張する|[Microsoft Purview データ マップでのラベル付け](/azure/purview/create-sensitivity-label) |

## <a name="end-user-documentation-for-sensitivity-labels"></a>機密度ラベルのエンド ユーザー向けのドキュメント

最も効果的なエンド ユーザー向けのドキュメントは、選択したラベル名と構成に関するカスタマイズされたガイダンスと手順です。 ラベル ポリシー設定 **[カスタム ヘルプ ページへのリンクをユーザーに提供する]** を使用して、このドキュメントへの内部リンクを指定することができます。 ユーザーは、**[秘密度]** ボタンから簡単にアクセスすることができます。

- 組み込みのラベル付けの場合: **[詳細]** メニュー オプション。
- Azure Information Protection 統合ラベル付けクライアントの場合: **[ヘルプとフィードバック]** メニュー オプション > [Microsoft Azure Information Protection] ダイアログ ボックスの **[詳細情報]** リンク。

カスタマイズしたドキュメントの提供に役立てるために、次のページを表示して、ユーザーのトレーニングに使用できるアイテムをダウンロードします。[秘密度ラベルのエンド ユーザー トレーニング](https://microsoft.github.io/ComplianceCxE/enduser/sensitivity/)。 

基本的な手順については、次のリソースを使用することもできます:

- [Office 内のファイルやメールに秘密度ラベルを適用する](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Office の秘密度ラベルに関する既知の問題](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Office のファイルとメールに秘密度ラベルを自動的に適用、または推奨する](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [機密度ラベルの自動適用または推奨に関する既知の問題](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Azure Information Protection の統合ラベル ユーザー ガイド](/azure/information-protection/rms-client/clientv2-user-guide)

秘密度ラベルを PDF ドキュメントの暗号化に適用する場合は、Windows または Mac で Microsoft Edge を使用して、これらのドキュメントを開くことができます。 詳細および代替リーダーについては、「[保護された PDF をサポートする PDF リーダー](/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)」を参照してください。
