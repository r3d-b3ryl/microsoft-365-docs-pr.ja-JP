---
title: GDPR のための Azure DevOps データ サブジェクト要求
keywords: Visual Studio Team Services、VSTS、Azure DevOps ドキュメント、プライバシー、GDPR
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: jitojo
ms.author: jominana
manager: douge
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: ce5ccb1961fe1751604b32bb5b37595b0884b395
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071486"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr"></a>GDPR のための Azure DevOps Services データ サブジェクト要求

EU [一般データ保護規則 (GDPR)](http://ec.europa.eu/justice/data-protection/reform/index_en.htm) では、ユーザー (この規則では*データ サブジェクト*と呼ばれる) に対して、*データ コントローラー*が収集した個人データを管理する権利が与えられます。データ コントローラー (または単に*コントローラー*) は、雇用主やその他の機関または組織です。GDPR の下では個人データは広範な定義がなされ、識別された、または識別可能な自然人に関連するあらゆるデータを指します。GDPR は、データ サブジェクトに対して、自分の個人データへの特定の権利を与えています。こうした権利には、個人データのコピーの取得、修正の要求、処理の制限、削除、別のコントローラーに移動できるようにするための電子形式での受信などがあります。データ サブジェクトがコントローラーに個人データに関するアクションの実行を求める正式な要求は、*データ サブジェクト要求* (DSR) と呼ばれます。

GDPR の一般的な情報については、[Service Trust Portal の GDPR セクション](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)を参照してください。

このガイドでは、Microsoft のツールを使用して、認証済みの (サインイン済みの) Azure DevOps Services (旧 Visual Studio Team Services) セッション中に収集された個人データをエクスポートまたは削除する方法について説明します。

## <a name="additional-privacy-information"></a>その他のプライバシー情報

[Microsoft のプライバシーに関する声明](https://privacy.microsoft.com/privacystatement)、[オンライン サービス使用条件 (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx)、および [Microsoft の GDPR コミットメント](/legal/gdpr)の記事では、弊社のデータ処理方法について説明しています。

## <a name="personal-data-we-collect"></a>Microsoft が収集する個人データ

Microsoft は、Azure DevOps Services を運用および改善するためにユーザーから 2 種類のデータを収集します。顧客データとシステムが作り出すログです。顧客データには、Azure DevOps Services がサービスを実行するために必要な、ユーザーを確認するためのトランザクション データおよび対話データが含まれます。システムが作り出すログには、製品分野と機能ごとに集計されたサービス使用状況のデータが含まれます。

## <a name="delete-azure-devops-data"></a>Azure DevOps データの削除

関連する Azure DevOps Services の顧客データを削除し、システムが作り出すログの中で見つかる、個人を特定できるデータを匿名化するための最初の手順は、Azure Active Directory (AAD) の ID アカウントまたは Microsoft アカウント (MSA) を削除する事です。Azure DevOps Services は、厳密な整合性、追跡可能性、および監査規則を持つ記録システムとして信頼されています。これらの義務は、GDPR に定められた削除および保持の義務に影響します。ID アカウントを削除しても、Azure DevOps 組織内の個々の ID に関連付けられたアーチファクトや記録は、修正、削除、変更されません。Azure DevOps 組織全体が削除されたときは、その組織内の個人を特定できるすべての関連データとシステムが作り出すログは、(Azure DevOps 組織の削除の必須期間である 30 日を経た後で) 弊社のシステムから削除されることを保証します。

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