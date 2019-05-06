---
title: Microsoft Teams および SharePoint Online サイトで高度な規制データを扱うには
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/03/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: セキュリティで保護された SharePoint Online チームサイトまたは Microsoft Teams のチームを作成し、最も重要で機密性の高いデジタル資産を保存します。
ms.openlocfilehash: d80be334f692f905ec70ae43f851d2b73801f4a0
ms.sourcegitcommit: dbcc32218489ab256b7eb343290fcccb9bc04e36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/02/2019
ms.locfileid: "33553326"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a>Microsoft Teams および SharePoint Online サイトで高度な規制データを扱うには

*このシナリオは、Microsoft 365 Enterprise の E3 および E5 の両バージョンに適用されます*

Microsoft 365 Enterprise には、高度な規制データを作成、保存、保護する一連のクラウドベースのサービスが用意されており、次のようなデータを扱います。

- 地域の規制を遵守しているデータ。
- 企業秘密、財務情報、人事情報、組織戦略など、組織にとって最も重要なデータ。

上記のビジネス ニーズを満たす Microsoft 365 Enterprise のクラウドベースのソリューションでは、以下のことが求められます。

- SharePoint Online チーム サイトまたは Microsoft Teams のチームの **[ファイル]** タブの、デジタル資産 (ドキュメント、スライド セット、スプレッドシートなど) を保存する。
- サイトまたはチームをロックダウンし、以下を防止する。
   - グループ メンバーシップ (これには、だれが SharePoint Online チームサイトにどんなアクセス許可のレベルでアクセスできるか、また、だれがそのアクセス許可を管理できるかが含まれる) によるユーザー アカウントの特定のセットのみへのアクセス。
   - サイトのメンバーから他のユーザーへのアクセス許可の付与。
   - サイトのメンバーでないユーザーからサイトへのアクセス要求。
- サイトまたはチーム内のドキュメントに保持ポリシーを定義する既定の方法として、SharePoint Online サイトやチーム用 Office 365 保持ラベルを構成します。
- ユーザーがファイルを組織の外部に送信できないようにします。
- サイトやチームの最も機密性の高いデジタル資産を暗号化する。
- 最も機密性の高いデジタル資産がサイト外で共有されて、その資産を開く場合にも、アクセス許可のあるユーザー アカウントの有効な資格情報が必要となるように、デジタル資産にアクセス許可を追加する。

次の表は、上記ソリューションの要件と Microsoft 365 Enterprise の機能を関連付けたものです。

|||
|:-------|:-----|
| **要件** | **Microsoft 365 Enterprise の機能** |
| デジタル資産の保存 | SharePoint Online チーム サイトと Office 365 のチーム |
| サイトのロックダウン | Azure AD グループおよび SharePoint Online チーム サイトのアクセス許可 |
| サイトのデジタル資産のラベル付け | Office 365 保持ラベル |
| ユーザーがファイルを組織外に送信できないようにする | Office 365 のデータ損失防止 (DLP) ポリシー |
| サイトのすべてのデジタル資産の暗号化 | Enterprise Mobility + Security (EMS) での Azure Information Protection サブラベル |
| サイトのデジタル資産へのアクセス許可の追加 | 手順 3: EMS での Azure Information Protection サブラベル |
|||

このソリューションでは、以下のものを既に展開している必要があります。

- 基盤インフラストラクチャの [ID](identity-infrastructure.md) フェーズ、および[情報保護](infoprotect-infrastructure.md)フェーズの手順 1 と 2。 
- [SharePoint Online](sharepoint-online-onedrive-workload.md) (SharePoint Online チームサイトで高度な規制データを扱う場合)。
- [Microsoft Teams](teams-workload.md) (Microsoft Teams のチームで高度な規制データを扱う場合)。

以下のフェーズでは、高度な規制データを扱う SharePoint Online サイトおよびチームの設計、構成、導入方法について、順を追って説明します。

架空の多国籍組織を表す Contoso 社が研究チーム向けに SharePoint Online サイトを設計した方法について確認するには、こちらの[構成例](contoso-sharepoint-online-site-for-highly-confidential-assets.md)をご覧ください。

>[!Note]
>チームで高度な規制データを扱う場合、高度な規制データを扱う SharePoint Online チーム サイトを最初に作成する必要があります。次に、SharePoint Online チーム サイトの Office 365 グループを使用する新しいチームを作成します。詳細については、フェーズ 2 の手順 4 を参照してください。
>

## <a name="identity-and-device-access-prerequisites"></a>ID とデバイスのアクセスの前提条件

チームまたは SharePoint Online サイトへのアクセスを保護するには、[ID とデバイスのアクセス ポリシー](identity-access-policies.md)と、[推奨される SharePoint Online アクセス ポリシー](sharepoint-file-access-policies.md)を構成していることを確認する必要があります。

## <a name="phase-1-design"></a>フェーズ 1: 設計

高度な規制データを扱う SharePoint Online サイトまたはチームを作成するには、まずその目的を特定する必要があります。たとえば、製造組織の研究開発部門では、既存製品の現在の設計仕様を保存し新製品の共同作業を行う場所として、SharePoint Online サイトが必要になります。この場合、研究開発部門のメンバーと、選択されている役員のみがサイトにアクセスすることができます。

目的に基づいて、以下のような必須の構成項目を決定します。

- SharePoint Online のアクセス許可一式と SharePoint グループのセット
- アクセス グループ一式 (SharePoint グループに追加する Azure AD セキュリティ グループとそのグループのメンバー)
- サイトに割り当てる Office 365 保持ラベルと、そのラベル用の一連の DLP ポリシー
- サイトに保存されている機密性の高いデジタル資産にユーザーが適用する Azure Information Protection サブラベルの設定

上記の項目を決定したら、それらの設定に基づき、フェーズ 2 でサイトを構成します。 

### <a name="step-1-an-isolated-sharepoint-online-site"></a>手順 1: 独立した SharePoint Online サイト

ロックダウンされたバージョンの SharePoint Online チーム サイトは、独立したサイトとして知られています。プライベート チーム サイトの既定の設定とは異なり、独立サイトは、以下ことを防ぐように構成されます。

- 指定したグループのメンバーではないユーザーへのアクセス。
- アクセスの要求。
- 指定されたグループの現在のメンバーによる、無許可のアクセス付与。
- アクセス グループのメンバーによるサイトの管理。

高度に規制された資産が含まれる SharePoint Online チーム サイトのセキュリティは、サイトの SharePoint 管理者のみが変更できます。

一連のアクセス許可レベル、SharePoint グループ、アクセス グループ、グループ メンバーのセットの決定方法の詳細については、「[独立した SharePoint Online チーム サイトの設計](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site)」を参照してください。

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a>手順 2: Office 365 保持ラベルと DLP ポリシー

SharePoint Online チーム サイトに適用されると、Office 365 保持ラベルは、サイトに保存されているすべてのデジタル資産を分類する既定のメソッドを提供します。
 
SharePoint Online サイトで高度な規制データを扱う場合は、どの Office 365 保持ラベルを使用するかを決定する必要があります。

Office 365 ラベルの設計の考慮事項については、「[Office 365 の分類とラベル](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)」を参照してください。

機密性の高い情報を保護し、偶発的または意図的な開示を防止するためには、DLP ポリシーを使用します。詳細については、DLP ポリシーの[概要](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)を参照してください。

SharePoint Online サイトで高度な規制データを扱うには、デジタル資産を外部のユーザーと共有しようとするユーザーをブロックするために、サイトに割り当てられた Office 365 保持ラベルの DLP ポリシーを構成する必要があります。 

### <a name="step-3-your-azure-information-protection-sub-label"></a>手順 3: Azure Information Protection サブラベル

最も機密性の高いデジタル資産を暗号化し、一連のアクセス許可を付与する場合、ユーザーは、Azure Information Protection クライアントを使用して Azure Information Protection のラベルを適用する必要があります。SharePoint Online サイトの Azure Information Protection のラベルを使用して高度な規制データを扱うには、スコープ指定されたポリシーに Azure Information Protection サブラベルを構成する必要があります。 

サブラベルは既存のラベルに含まれます。たとえば、機密性の高いラベルに含まれるラベルとして、研究開発のサブラベルを作成することができます。スコープ指定されたポリシーは、ユーザーのサブセットにのみ適用されるポリシーです。SharePoint Online サイトで高度な規制データを扱う場合、スコープは、サイトのアクセス グループのメンバーである一連のユーザーになります。

適用したサブラベルの設定が行われると、サブラベルは資産と共に移動します。サブラベルをダウンロードしてサイト外で共有しても、アクセス許可を持つ認証済みのユーザー アカウントしか、サブラベルを開くことはできません。

### <a name="design-results"></a>設計の結果

以下を決定しました。

- SharePoint グループとアクセス許可レベルのセット
- アクセス グループと、そのグループのメンバーそれぞれのアクセス許可レベルのセット
- 適切な Office 365 保持ラベルと、そのラベルに関連付けられている DLP ポリシー
- 暗号化とアクセス許可を含む Azure Information Protection サブラベルの設定

## <a name="phase-2-configure"></a>フェーズ 2: 構成

このフェーズでは、フェーズ 1 で決定した設定を実装し、高度な規制データを扱う SharePoint Online サイトを作成します。

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a>手順 1: 独立した SharePoint Online チーム サイトを作成し構成する

「[独立した SharePoint Online チーム サイトの展開](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)」の手順を参照しながら、以下を実行します。

- サイトで使用する SharePoint のアクセス許可レベルそれぞれのアクセス グループを作成してデータを設定する。
- 独立したチーム サイトを作成して構成する。

### <a name="step-2-configure-the-site-for-an-office-365-retention-label-dlp-policy"></a>手順 2: Office 365 保持ラベルの DLP ポリシー向けにサイトを構成する

「[Office 365 ラベルと DLP による SharePoint Online ファイルの保護](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)」の手順を参照しながら、以下を実行します。

- Office 365 保持ラベルを特定または作成し、独立した SharePoint Online サイトに適用する。
- ユーザーが組織外の SharePoint Online サイトでデジタル資産を共有しようとする場合にユーザーをブロックする DLP ポリシーを作成して構成する。

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a>手順 3: サイト用の Azure Information Protection サブレベルを作成する

「[Azure Information Protection で SharePoint Online ファイルを保護する](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)」の手順を参照しながら、以下を実行します。 

- スコープ指定されたポリシーに Azure Information Protection サブラベルを作成して構成する。
- Azure Information Protection クライアントをユーザーのコンピューターに展開する。

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a>手順 4 (省略可能): 高度な規制データを扱うチームを作成する

高度な規制データを扱うチームが必要な場合は、まず高度な規制データを扱う SharePoint Online サイトを作成します。最初のプライベートの SharePoint Online チーム サイトを作成するときに、Office 365 グループ名を指定します。

高度な規制データを扱う SharePoint Online サイトが完全に構成されたら、次の手順を実行して、高度な規制データを扱うチームに変換します。

1. Office 365 にサインインします。
2. **[Microsoft Office Home]** タブで、**[チーム]** をクリックします。
3. **[チームに参加またはチームを作成する]** ウィンドウの **[Microsoft Teams]** タブで、**[チームを作成する]** をクリックします。
4. **[チームを作成する]** ウィンドウで **[既存の Office 365 グループからチームを作成する]** をクリックします。
5. Office 365 グループの一覧から、高度な規制データを扱う SharePoint Online サイトに対応する Office 365 グループの名前を選択し、**[チームを選択する]** をクリックします。

新しいチームの **[ファイル]** タブには、対応する SharePoint Online サイトの**ドキュメント**領域の**一般**フォルダーの内容が一覧表示されます。チームの SharePoint Online サイトの残りのリソースを表示するには、省略記号をクリックし、**[SharePoint で開く]** をクリックします。

### <a name="configuration-results"></a>構成の結果

以下を構成しました。

- SharePoint Online の独立したサイト
- 独立した SharePoint Online サイトに割り当てられている Office 365 保持ラベル
- Office 365 保持ラベルの DLP ポリシー
- スコープ指定されたポリシーの Azure Information Protection サブラベル。スコープ指定されたポリシーは、ユーザーがサイトに保存されている最も機密性の高いデジタル資産に適用できるポリシーで、保存先のサイトでは資産の暗号化とアクセス許可の付与が行われる
- SharePoint Online サイトをベースとした高度な規制データを扱うチーム (必要な場合に作成)

## <a name="phase-3-drive-user-adoption"></a>フェーズ 3: ユーザーによる採用を主導する

SharePoint Online サイトまたはチームが高度な規制データを保護できるのは、機密性の高いデジタル資産の保存とその資産へのアクセスのために、それがコンスタントに使用される場合だけです。このフェーズは、ユーザーのやり方の変更に依存する最も難しいフェーズとなります。 

たとえば、役員が機密ファイルを USB ドライブや個人のクラウドベースのストレージ ソリューションに保存していた場合、その役員は、高度な規制データを扱う SharePoint Online サイトまたはチームだけに機密ファイルを保存するようになる必要があります。

### <a name="step-1-train-your-users"></a>手順 1: ユーザーをトレーニングする

構成が完了したら、サイトのアクセス グループのメンバーである一連のユーザーを以下の面でトレーニングします。

- 貴重な資産を保護するために新しいサイトやチームを使用することの重要性と、高度な規制データのリークによって生じる事態 (法的影響、規制上の罰金、ランサムウェア、競争力の低下など)。
- サイトとその資産へのアクセス方法。
- サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。
- DLP ポリシーを使用して、外部からのファイルの共有をできないようにする方法。
- Azure Information Protection クライアントを使用して、構成したサブラベルで最も機密性の高いデジタル資産にラベル付けをする方法。
- サイトやチームから資産がリークした場合でも、Azure Information Protection サブラベルによって資産を保護する方法。

このトレーニングには、ユーザーが上記の操作とその結果を体感できるように、実践的な演習を組み込む必要があります。

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>手順 2: 使用状況とファイルの定期的なレビューの実施

トレーニングの数週間後、SharePoint Online サイトまたはチームの SharePoint 管理者は次のことができます。

- サイトまたはチームの使用状況を分析し、それが期待された使用法と一致しているかを比較する。
- 機密性の高いファイルに Azure Information Protection サブラベルが正しくラベル付けされていることを確認する。

必要に応じて、ユーザーの再トレーニングを行います。

### <a name="user-adoption-results"></a>ユーザーによる採用の結果

機密性の高いデジタル資産は、高度な規制データを扱う SharePoint Online サイトまたはチームだけに保存され、最も機密性の高い資産には Azure Information Protection サブラベルが適用されます。

## <a name="see-also"></a>関連項目

[展開ガイド](deploy-microsoft-365-enterprise.md)

[テスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[開発/テスト環境の SharePoint Online サイトをセキュリティで保護する](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
