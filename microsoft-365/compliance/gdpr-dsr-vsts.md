---
title: GDPR および CCPA のための Azure DevOps データ サブジェクト要求
keywords: Visual Studio Team Services、VSTS、Azure DevOps ドキュメント、プライバシー、GDPR、CCPA
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: robmazz
f1.keywords:
- NOCSH
ms.author: robmazz
manager: laurawi
ms.collection:
- GDPR
- M365-security-compliance
ms.workload:
- multiple
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 4ae98f6e396bdca0f1f1a4d6d360cf062878ba73
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073274"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR および CCPA のための Azure DevOps Services データ サブジェクト要求

EU [一般データ保護規則 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) では、ユーザー (この規則では*データ サブジェクト*と呼ばれる) に対して、*データ コントローラー*が収集した個人データを管理する権利が与えられます。データ コントローラー (または単に*コントローラー*) は、雇用主やその他の機関または組織です。GDPR の下では個人データは広範な定義がなされ、識別された、または識別可能な自然人に関連するあらゆるデータを指します。GDPR は、データ サブジェクトに対して、自分の個人データへの特定の権利を与えています。こうした権利には、個人データのコピーの取得、修正の要求、処理の制限、削除、別のコントローラーに移動できるようにするための電子形式での受信などがあります。データ サブジェクトがコントローラーに個人データに関するアクションの実行を求める正式な要求は、*データ サブジェクト要求* (DSR) と呼ばれます。

同様に、カリフォルニア州消費者プライバシー法 (CCPA) では、それらの個人情報の削除、アクセスおよび受信 (移植性) の権利などの GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。  また、CCPA では、特定の開示、権利の行使を選択する際の差別に対する保護、“売上“ として分類された特定のデータ転送の “オプトアウト/オプトイン“ 要件を規定します。 「販売」は広く定義されており、有価約因に関するデータの共有を含みます。 CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](offering-ccpa.md)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](ccpa-faq.md)」を参照してください。

GDPR の一般的な情報については、[Service Trust Portal の GDPR セクション](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) を参照してください。

このガイドでは、Microsoft のツールを使用して、認証済みの (サインイン済みの) Azure DevOps Services (旧 Visual Studio Team Services) セッション中に収集された個人データをエクスポートまたは削除する方法について説明します。

## <a name="additional-privacy-information"></a>その他のプライバシー情報

[Microsoft のプライバシーに関する声明](https://privacy.microsoft.com/privacystatement)、[オンライン サービス使用条件 (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx)、および [Microsoft の GDPR コミットメント](/legal/gdpr)の記事では、弊社のデータ処理方法について説明しています。

## <a name="personal-data-we-collect"></a>Microsoft が収集する個人データ

Microsoft では、Azure DevOps Services の運用および向上のために、ユーザーのデータを収集します。 Azure DevOps Services では、2 つのカテゴリのデータを収集します。つまり、顧客データとシステム生成ログです。 顧客データには、サービスを運用するために Azure DevOps Services で必要とされる、特定のユーザーを識別可能なトラザクション データおよび相互作用的データが含まれます。 システム生成ログには、各製品領域と機能について集計されたサービスの利用状況データが含まれます。

## <a name="delete-azure-devops-data"></a>Azure DevOps データの削除

関連付けられた Azure DevOps Services の顧客データの削除、およびシステム生成ログで確認される個人を識別可能なデータの匿名化の最初のステップは、Azure Active Directory (AAD) の ID アカウントまたは Microsoft アカウント (MSA) を閉じることです。 Azure DevOps Services は、完全な統合性、追跡可能性、監査ルールを用いたレコードのシステムとして信頼されています。 これらの既存の義務は、GDPR の削除と保持の義務に影響を与えます。 IDアカウントを閉じても、Azure DevOps 組織の個別 ID に関連付けられた成果物およびレコードを修正、削除、変更することはありません。 Azure DevOps 組織全体が削除さたときに、すべての関連付けられた個人を識別可能なデータおよびその組織で確認されるシステム生成ログが、システムから削除されることを確実にしました (Azure DevOps 組織で必要な 30 日間の倫理的な削除の期間後)。

## <a name="export-azure-devops-data"></a>Azure DevOps データのエクスポート

コントローラーは、Azure DevOps サービスへのサインインに使用される ID プロバイダー (MSA または AAD) に応じて、2 つの方法のいずれかで、データ サブジェクトから収集された顧客データとシステム生成ログをエクスポートできます。

- Azure サブスクリプションに関連付けられた AAD アカウントや MSA アカウントなど、Azure テナントに裏付けられたアカウントを使用して認証を行うユーザーは、「[GDPR のための Azure データ サブジェクト要求](gdpr-dsr-azure.md)」の手順を実行できます。

- MSA ID を使用して認証を行うユーザーは、この[プライバシー要求サイト](https://www.microsoft.com/concern/privacyrequest-msa)を使用して、複数の Microsoft サービス間で MSA ID に関連付けられたアクティビティ データを表示できます。このシナリオでは、ユーザーは自分の個人データのコントローラーです。

## <a name="export-or-delete-issues"></a>エクスポートまたは削除の問題

AAD ID の場合、Azure Portal からデータをエクスポートまたは削除する際に問題が発生したときは、Azure Portal の **[ヘルプとサポート]** ブレードに移動し、**[サブスクリプションの管理]** > **[他のセキュリティとコンプライアンスの要求]** > **[プライバシー ブレードと GDPR 要求]** で新しいチケットを送信します。

MSA ID の場合、プライバシー要求サイトからデータをエクスポートする際に問題が発生したときは、[プライバシー要求サイト](https://www.microsoft.com/concern/privacyrequest-msa)にログオンし、要求 Web フォームを介して Microsoft プライバシー チームからのヘルプへの要求を送信します。

## <a name="learn-more"></a>詳細の表示

Microsoft は、ユーザーの Azure DevOps Services データが今後も確実に例外なく保護され、公開されないことを確約します。弊社がユーザーの Azure DevOps Services データを保護する方法の詳細については、[Azure DevOps Services データ保護の概要](/vsts/articles/team-services-security-whitepaper?view=vsts)に関するホワイトペーパーを参照してください。

## <a name="see-also"></a>関連項目

- [一般公開されているエンタープライズ ソフトウェア製品のお客様に対する Microsoft の GDPR コミットメント](https://docs.microsoft.com/legal/gdpr)
- [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Microsoft プライバシー ダッシュボード](https://account.microsoft.com/privacy)
- [Microsoft Privacy Response Center](https://aka.ms/userprivacysite)
- [GDPR のための Azure データ サブジェクト要求](gdpr-dsr-azure.md)
