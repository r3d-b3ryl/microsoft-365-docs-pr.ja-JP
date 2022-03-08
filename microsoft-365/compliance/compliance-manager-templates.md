---
title: Microsoft コンプライアンス マネージャーでの評価テンプレートの操作
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンス マネージャーで評価を構築するためのテンプレートを使用および管理する方法について説明します。 書式設定されたファイルを使用してテンプレートを作成Excelします。
ms.openlocfilehash: 6885008e58c1e1289723a6d8c1ee4e04d16740b0
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317725"
---
# <a name="learn-about-assessment-templates-in-compliance-manager"></a>コンプライアンス マネージャーの評価テンプレートの詳細

**この記事では、次の情報を参照してください。** テンプレート **の動作と評価** テンプレート **ページ** からテンプレートを管理する方法について説明します。 新しいテンプレートの作成 **、** 既存のテンプレートの拡張と変更、テンプレート データの書式設定、テンプレート レポートのエクスポートExcel説明 **します**。

> [!IMPORTANT]
> 組織で使用できる評価テンプレートは、ライセンス契約によって異なります。 [詳細を確認します](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="templates-overview"></a>テンプレートの概要

テンプレートは、コンプライアンス マネージャーで評価を作成するためのコントロールのフレームワークです。 当社の包括的なテンプレートセットは、データの収集と使用を管理する国内、地域、および業界固有の要件を組織が遵守するのに役立ちます。

## <a name="template-versions-microsoft-and-universal"></a>テンプレートのバージョン: Microsoft とユニバーサル

テンプレートは、EU GDPR テンプレートや ISO/IEC 27701:2019 テンプレートなど、基になる認定または規制と同じ名前で参照されます。

コンプライアンス管理は、さまざまな種類の製品を評価するために使用できます。 ベースライン以外のすべてのテンプレートには、Microsoft 365 などの定義済み製品に適用される少なくとも 1 つのバージョンと、他の製品に合わせて調整できるユニバーサル バージョンがあります。 ユニバーサル テンプレートからの評価は一般化されますが、複数の製品間で組織のコンプライアンスを簡単に追跡できるので、汎用性が向上します。

米国政府機関 (Community) (GCC) 中程度、GCC 高、および国防総省 (DoD) のお客様は現在、ユニバーサル テンプレートを使用できません。

## <a name="template-availability-and-licensing"></a>テンプレートの可用性とライセンス

コンプライアンス マネージャーには、組み込みテンプレートとプレミアム テンプレートの 2 つのカテゴリがあります。

1. **含まれるテンプレートは** 、コンプライアンス マネージャー のライセンスによって付与され、主要な規制と要件をカバーします。 ライセンス契約で使用できるテンプレートの詳細については、「ライセンスの詳細 [」を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)。
2. **プレミアムのニーズ** とシナリオをカバーするテンプレートは、テンプレート ライセンスを購入することで入手できます。

評価の作成を開始すると、コンプライアンス マネージャーはアクティブなテンプレートの数を追跡し、使用状況を監視できます。 詳細については、「アクティブなテンプレート [と非アクティブなテンプレート」を参照してください](compliance-manager-templates.md#active-and-inactive-templates)。

コンプライアンス マネージャー [で使用できるテンプレートの](compliance-manager-templates-list.md) 完全な一覧を表示します。

### <a name="purchase-premium-template-licenses"></a>プレミアム テンプレート ライセンスの購入

テンプレート ライセンスは、コンプライアンス マネージャーのライセンス契約に応じて、1 つ以上の方法で取得できます。 購入が完了すると、テンプレートは 48 時間以内にテナントで利用できます。

**商用およびGCCモデレート**

商用アカウントGCC管理センターでテンプレート ライセンスを購入できます (サブスクリプション、ライセンス、請求の詳細[については、詳細を参照してください](/microsoft-365/commerce/))。 購入するライセンスの数と支払いプランを選択します。

購入リンク:

- [商用](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/46E9BF2A-3C8D-4A69-A7E7-3DA04687636D)
- [GCC モデレート](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/3129986d-5f4b-413b-a34b-b706db5a7669)

また、プログラムまたはボリューム ライセンスへの参加を通クラウド ソリューション プロバイダー[ライセンス](https://partner.microsoft.com/membership/cloud-solution-provider)[を取得できます](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)。

**GCCアカウントと DOD アカウント**

GCC DOD アカウントは、ボリューム ライセンスを使用してテンプレート ライセンスを[購入する必要があります](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)。

### <a name="try-out-premium-templates"></a>プレミアム テンプレートを試す

購入前にプレミアム テンプレートを試す場合は、ライセンスの試用版を入手することもできます。 試用版ライセンスは、90 日間、最大 25 のテンプレートに対して良好です。 試用版ライセンスを取得すると、テンプレートは 48 時間以内にテナントで利用できます。

組織にコンプライアンス マネージャーの商用ライセンスがある場合は、「Microsoft Compliance Manager プレミアム評価の無料試用版について」で試用版を開始する方法 [について説明します](compliance-easy-trials-compliance-manager-assessments.md)。

組織がユーザーライセンスまたは DOD ライセンスGCC場合は、組織の適切な試用版リンクを選択します。

- [GCC モデレート](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/87ed2908-0a8d-430a-9635-558ed42b581f)
- [GCC High](https://portal.office365.us/SubscriptionDetails?OfferId=e14362d7-2c11-4a43-9c92-59f1b499b96a)
- [DOD](https://portal.apps.mil/Commerce/Trial.aspx?OfferId=17e28290-7de6-41a9-af30-f6497396ab2e)

#### <a name="active-and-inactive-templates"></a>アクティブなテンプレートと非アクティブなテンプレート

テンプレートはアクティブまたは非アクティブとしてアクティブ状態を表示します。

- テンプレートは、そのテンプレート **から評価** を作成するとアクティブと見なされます。
- 組織が評価に **テンプレート** を使用しない場合、テンプレートは非アクティブと見なされます。

購入したプレミアム テンプレートに評価をリンクすると、そのテンプレートは 1 年間アクティブになります。 キャンセルしない限り、購入は自動的に更新されます。

#### <a name="activated-templates-counter"></a>アクティブ化されたテンプレート カウンター

評価ページと評価テンプレート ページには、上部の **近くにアクティブ化されたテンプレート** カウンターがあります。 このカウンターには、ライセンス契約に従って使用する資格がある数の中で使用されているテンプレートの数が表示されます。 テンプレートの使用は、認定レベルでカウントされます。

たとえば、カウンターに 2/5 が表示されている場合、使用できる 5 つのテンプレートの中から 2 つのテンプレートがアクティブ化されています。

カウンターに 5/2 が表示されている場合は、組織が制限を超え、使用しているプレミアム テンプレートの 3 つを購入する必要があります。

定義済みの製品のテンプレート (Microsoft 365など) には、同じテンプレートのユニバーサル バージョンとの共同ライセンスがあります。 これにより、複数の製品で同じ基になる認定を使用できます。 同じテンプレートのどちらかまたは両方のバージョンを使用すると、アクティブ化されたテンプレートは 1 つのみカウントされます。

詳細については、「コンプライアンス マネージャーの [ライセンス ガイダンス」を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)。

## <a name="view-and-manage-templates"></a>テンプレートの表示と管理

コンプライアンス マネージャーの [評価テンプレート] ページには、テンプレートの一覧と、テンプレートに関する主要な詳細が表示されます。 このリストには、コンプライアンス マネージャーが提供するテンプレートのほか、組織が変更または作成したテンプレートも含まれます。 フィルターを適用して、認定、製品範囲、国、業界、作成者、および評価の作成にテンプレートが有効になっているかどうかに基づいてテンプレートを検索できます。

行からテンプレートを選択して、詳細ページを表示します。 このページには、テンプレートの説明と、認定、スコープ、およびコントロールの詳細に関する詳細情報が含まれています。 このページでは、適切なボタンを選択して、評価の作成、テンプレート データのエクセルへのエクスポート、またはテンプレートの変更を行うことができます。

## <a name="create-an-assessment-template"></a>評価テンプレートの作成

コンプライアンス マネージャーでカスタム評価用の独自の新しいテンプレートを作成するには、特別に書式設定されたスプレッドシートExcelを使用して、必要なコントロール データを組み立てます。 スプレッドシートが完成すると、コンプライアンス マネージャーにインポートされます。 詳細については、「評価テンプレートの [作成」を参照してください](compliance-manager-templates-create.md)。

## <a name="modify-an-assessment-template"></a>評価テンプレートの変更

コンプライアンス マネージャーで評価を操作する場合は、作成した評価テンプレートを変更できます。 このプロセスは、テンプレートの作成プロセスと似ています。テンプレート データを含む書式設定されたExcelファイルをアップロードします。 変更を加える方法と、維持するデータを保持する方法の詳細については、「評価テンプレートの変更 [」を参照してください](compliance-manager-templates-modify.md)。

## <a name="extend-an-assessment-template"></a>評価テンプレートを拡張する

コンプライアンス マネージャーには、独自のコントロールと改善アクションを既存のテンプレートに追加するオプションがあります。 このプロセスは、テンプレートの拡張と呼ばれる。 テンプレートを拡張するには、Microsoft の評価テンプレートまたはユニバーサル評価テンプレートを拡張するかどうかに応じて、テンプレート データに追加する特別な手順を使用します。 詳細については、「評価テンプレートを [拡張する」を参照してください](compliance-manager-templates-extend.md)。

## <a name="format-assessment-template-data-in-excel"></a>評価テンプレート のデータの書式を設定Excel

コンプライアンス マネージャーで評価テンプレートを作成、変更、または拡張する場合は、特定のExcelスキーマを使用するスプレッドシートを使用します。 ファイルが正しくインポートされるようにするには、これらの仕様に従う必要があります。 詳細については、「評価テンプレート データ[の書式設定」を参照Excel](compliance-manager-templates-format-excel.md)。

## <a name="export-a-template"></a>テンプレートのエクスポート

テンプレートのすべてのデータをExcelファイルをエクスポートできます。 テンプレートを変更するには、テンプレートをエクスポートする必要があります。これは、変更プロセスで編集およびアップロードExcelファイル[になります。](compliance-manager-templates-modify.md) 新しいカスタム テンプレートの作成中にデータを使用する場合は、参照用にテンプレートをエクスポートすることもできます。

テンプレートをエクスポートするには、テンプレートの詳細ページに移動し、[テンプレートにエクスポート] ボタン **Excel** します。

コンプライアンス マネージャー テンプレートから拡張したテンプレートをエクスポートする場合、エクスポートされるファイルには、テンプレートに追加した属性だけが含まれます。 エクスポートされたファイルには、Microsoft が提供する元のテンプレート データは含めされません。 このようなレポートを取得するには、評価レポートをエクスポートする [手順を参照してください](compliance-manager-assessments.md#export-an-assessment-report)。