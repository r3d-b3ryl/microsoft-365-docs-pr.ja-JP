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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 組織のデータを保護するために秘密度ラベルの実装を開始する準備はできていますが、どこから始めればよいかわかりませんか? ラベル付けの移行に役立つ実用的なガイダンスをお読みください。
ms.openlocfilehash: 2c23246f17a8d9ea9681017dca28e144f3088604
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245960"
---
# <a name="get-started-with-sensitivity-labels"></a>秘密度ラベルの使用を開始する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

秘密度ラベルの概要とそれらが組織のデータを保護する方法の詳細については、「[秘密度ラベルの詳細](sensitivity-labels.md)」を参照してください。

[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) がある場合、ラベルを統合ラベル付けプラットフォームに移行する必要があるかどうか、および使用するラベル付けクライアントを決定します。
- [自分のテナントが統合されたラベル付けプラットフォームにあるかどうかを判断するにはどうすればよいですか?](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [Windows コンピューターに使用するラベル付けクライアントを選択する](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

秘密度ラベルを使用して組織のデータを保護する準備ができたら、次の手順に従います。

1. **ラベルを作成する。** コンテンツのさまざまなレベルに対する組織の分類方法に従って、秘密度ラベルを作成して名前を付けます。 ユーザーにとって意味のある、一般的な名前または用語を使用します。 分類方法がまだ確率していない場合は、「個人用」、「パブリック」、「一般」、「社外秘」、および「極秘」などのラベル名を使って使用開始することを検討してください。 サブラベルを使用すると、類似したラベルをカテゴリ別にグループ化できます。 ラベルを作成するときは、ユーザーが適切なラベルを選択できるよう、ツールヒントのテキストを使用します。
    
    分類法を定義するためのより広範なガイダンスについては、[Service Trust Portal](https://aka.ms/DataClassificationWhitepaper) のホワイト ペーパー「データ分類と秘密度ラベルの分類」をダウンロードしてください。

2. **各ラベルの機能を定義する。** 各ラベルに関連付ける必要がある保護設定を構成します。 たとえば、"一般" ラベルなどの秘密度の低いコンテンツには単にヘッダーやフッターを適用し、"社外秘" ラベルなどの秘密度のより高いコンテンツには透かしや暗号化を適用する、といったことができます。

3. **ラベルを発行する。** 秘密度ラベルの構成が完了したら、ラベル ポリシーを使用してラベルを公開します。 ラベルを使用する必要があるユーザーとグループおよび使用するポリシー設定を決定します。 1 つのラベルは再利用できます。 一度定義したラベルは、異なるユーザーに割り当てる複数のラベル ポリシーに含めることができます。 たとえば、ラベル ポリシーをごく少数のユーザーに対して適用して、秘密度ラベルを試験運用することができます。 組織全体に対してラベルを展開する準備ができたら、ラベルの新しいラベル ポリシーを作成し、今回はすべてのユーザーを指定することができます。

秘密度ラベルを展開して適用するための基本的な流れ:

![秘密度ラベルのワークフローを示す図](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>秘密度ラベルのサブスクリプションとライセンスの要件

秘密度ラベルはさまざまな異なるサブスクリプションに対応しており、ユーザーのライセンス要件は使用する機能によって異なります。

2020 年 4 月 1 日時点の Microsoft 365 コンプライアンス機能の利点を得られるようにユーザーにライセンス付与するオプションを確認するには、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)」を参照してください。 秘密度ラベルの詳細については「[情報保護](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)」セクションを参照し、関連する PDF または Excel をダウンロードしてください。

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>機密ラベルの作成と管理に必要なアクセス許可

秘密度ラベルを作成するコンプライアンス チームのメンバーは、Microsoft 365 コンプライアンス センター、Microsoft 365 セキュリティ センター、またはセキュリティ/コンプライアンス センターへのアクセス許可を持っている必要があります。 

既定では、テナントのグローバル管理者はこれらの管理センターへのアクセス権を所有し、コンプライアンス責任者や他のユーザーにアクセス権を付与できます (テナント管理者が持つすべての権限を付与する必要はありません)。この委任された制限付き管理者アクセス許可については、ユーザーを [**コンプライアンス データ管理者**]、[**コンプライアンス管理者**]、または [**セキュリティ管理者**] 役割グループに追加します。 

既定の役割を使用する代わりに、新しい役割グループを作成し、**秘密度ラベル管理者**の役割または**組織の構成**の役割をこのグループに追加できます。 読み取り専用の役割の場合は、**秘密度ラベルリーダー**を使用します。 

ユーザーを既定の役割に追加する方法、または独自の役割グループを作成する方法については、「[ユーザーに Office 365 セキュリティ/コンプライアンス センターへのアクセス権を付与する](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)」をご覧ください。

これらのアクセス許可は、機密ラベルとそのラベル ポリシーの作成と構成を行う場合にのみ必要です。 アプリまたはサービスでラベルを適用するためには必要はありません。 秘密度ラベルに関連する特定の構成に追加のアクセス許可が必要な場合、それらのアクセス許可はそれぞれのドキュメントの説明に記載されています。

## <a name="deployment-strategy-for-sensitivity-labels"></a>秘密度ラベルの展開戦略

組織の秘密度ラベルの展開戦略を成功させるには、ビジネス要件と技術要件、概念実証テスト、内部チェックポイントと承認、運用環境の最終的な展開を特定し管理する作業仮想チームを作成します。

次のセクションの表を使用して、最も影響力のあるビジネス要件にマッピングされる上位 1 つまたは 2 つのシナリオを特定することをお勧めします。 これらのシナリオが展開されたら、リストに戻り、次に展開する優先順位の 1 つまたは 2 つを特定します。

追加の一般的なガイダンスは、ダウンロード可能な「Microsoft 365 Information Protection & コンプライアンス展開促進ガイド」を参照してください。 詳細については、「[Microsoft の情報保護とコンプライアンス展開の促進ガイド](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-compliance-deployment/ba-p/1403493)」ブログ投稿を参照してください。

## <a name="common-scenarios-for-sensitivity-labels"></a>秘密度ラベルの一般的なシナリオ

すべてのシナリオで、[秘密度ラベルとそのポリシーを作成して構成する](create-sensitivity-labels.md)必要があります。

|必要な作業...|ドキュメント|
|----------------|---------------|
|Office アプリの秘密度ラベルを管理して、コンテンツの作成時にラベルを付けられるようにする (すべてのプラットフォームでの手動によるラベル付けのサポートを含む) |[Office アプリで秘密度ラベルを使用する](sensitivity-labels-office-apps.md)|
|ユーザーが Office アプリ、エクスプローラー、および PowerShell を使用して、Windows コンピューターからファイルにラベルを付けて保護できるようにする|[Windows 用のAzure Information Protection 統合ラベル付けクライアント](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)|
|秘密度ラベルを使用してドキュメントやメールを暗号化し、そのコンテンツにアクセスできるユーザーとその使用方法を制限する |[秘密度ラベルを使用して暗号化を適用してコンテンツへのアクセスを制限する](encryption-sensitivity-labels.md)|
|ドキュメントが暗号化されている場合でも、共同編集、電子情報開示、データ損失防止、検索をサポートし、Office on the web の秘密度ラベルを有効にする | [SharePoint および OneDrive で Office ファイルの機密度ラベルを有効にする](sensitivity-labels-sharepoint-onedrive-files.md)
|秘密度ラベルをドキュメントとメールに自動的に適用する | [機密ラベルをコンテンツに自動的に適用する](apply-sensitivity-label-automatically.md)|
|秘密度ラベルを使用して、Teams や SharePoint のコンテンツを保護する |[Microsoft Teams、Microsoft 365 グループ、SharePoint サイトで秘密度ラベルを使用する)](sensitivity-labels-teams-groups-sites.md)|
|特定の感度ラベルを持つファイルまたはメールをユーザーが共有しないように、または警告します。 |[DLP ポリシー(プレビュー)で感度ラベルを条件として使用する](dlp-sensitivity-label-as-condition.md) |
|オンプレミスのデータ ストアに保存されているファイルを検出、ラベル付け、保護する |[ファイルを自動的に分類および保護するための Azure Information Protection スキャナーを展開する](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|クラウドのデータ ストアに保存されているファイルを検出、ラベル付け、保護する|[クラウドに保存されている規制対象および機密データを検出、分類、ラベル付け、保護する](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Power BI で秘密度ラベルを適用して表示し、データのエクスポート時にデータを保護します。|[Power BI でのデータ保護](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview)|
|組織で秘密度ラベルがどのように使用されているかを監視し、理解する|[データを把握する - データ分類の概要](data-classification-overview.md) <br /><br /> [ラベル分析によるラベル使用状況を表示する](label-analytics.md)|
|秘密度ラベルの適用をサード パーティ製アプリやサービスに拡大する|[Microsoft 情報保護 SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|

## <a name="end-user-documentation-for-sensitivity-labels"></a>機密度ラベルのエンド ユーザー向けのドキュメント

最も効果的なエンド ユーザー向けのドキュメントは、選択したラベル名と構成に関するカスタマイズされたガイダンスと手順です。 ただし、基本的な手順については次のリソースを使用できます。

- [Office 内のファイルやメールに機密ラベルを適用する](https://support.microsoft.com/ja-JP/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Office の秘密度ラベルに関する既知の問題](https://support.microsoft.com/ja-JP/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Office のファイルとメールに秘密度ラベルを自動的に適用、または推奨する](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [機密度ラベルの自動適用または推奨に関する既知の問題](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Azure Information Protection の統合ラベル ユーザー ガイド](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-user-guide)

秘密度ラベルを PDF ドキュメントの暗号化に適用する場合は、Windows または Mac で Microsoft Edge を使用して、これらのドキュメントを開くことができます。 詳細および代替リーダーについては、「[保護された PDF をサポートする PDF リーダー](https://docs.microsoft.com/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)」を参照してください。
