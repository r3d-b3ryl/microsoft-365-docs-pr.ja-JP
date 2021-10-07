---
title: Microsoft コンプライアンス マネージャーでの評価テンプレートの操作
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.custom: admindeeplinkMAC
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンス マネージャーで評価を構築するためのテンプレートを使用および管理する方法について説明します。 書式設定されたファイルを使用してテンプレートを作成Excelします。
ms.openlocfilehash: 9b3ee570b116d501ec092fd417e5b2fc1ca07251
ms.sourcegitcommit: 81533e5d3e1aee0823539a7c9bdc20dba6541a02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2021
ms.locfileid: "60223437"
---
# <a name="learn-about-assessment-templates-in-compliance-manager"></a>コンプライアンス マネージャーの評価テンプレートの詳細

**この記事では、次の情報を参照してください。** テンプレート **の動作と評価** テンプレート **ページ** からテンプレートを管理する方法について説明します。 新しいテンプレートの作成 **、** 既存のテンプレートの拡張と変更、Excel を使用したテンプレート **データの** 書式設定、およびテンプレート レポートのエクスポートに関する手順を取得 **します**。

> [!IMPORTANT]
> 組織で使用できる評価テンプレートは、ライセンス契約によって異なります。 [詳細を確認します](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="templates-overview"></a>テンプレートの概要

テンプレートは、コンプライアンス マネージャーで評価を作成するためのコントロールのフレームワークです。 当社の包括的なテンプレートセットは、データの収集と使用を管理する国内、地域、および業界固有の要件を組織が遵守するのに役立ちます。

テンプレートは、EU GDPR テンプレートや ISO/IEC 27701:2019 テンプレートなど、基になる認定または規制と同じ名前で参照されます。 コンプライアンス管理はさまざまな種類の製品を評価するために使用できます。各テンプレートには、Microsoft 365 に適用されるバージョンと、選択した製品に合わせてカスタマイズできるユニバーサル バージョンの 2 つのバージョンがあります。

米国政府Community (GCC) 中程度、GCC 高、および国防総省 (DoD) のお客様は現在、Microsoft 365 テンプレート バージョンを使用できますが、ユニバーサルではありません。

## <a name="template-availability-and-licensing"></a>テンプレートの可用性とライセンス

コンプライアンス マネージャーには、組み込みテンプレートとプレミアム テンプレートの 2 つのカテゴリがあります。

1. **含まれるテンプレートは** 、コンプライアンス マネージャー のライセンスによって付与され、主要な規制と要件をカバーします。 ライセンス契約で使用できるテンプレートの詳細については、「ライセンスの詳細」 [を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)。
2. **プレミアムのニーズ** とシナリオをカバーするテンプレートは、テンプレート ライセンスを購入することで入手できます。

評価の作成を開始すると、コンプライアンス マネージャーはアクティブなテンプレートの数を追跡し、使用状況を監視できます。 詳細については、「アクティブなテンプレート [と非アクティブなテンプレート」を参照してください](compliance-manager-templates.md#active-and-inactive-templates)。

コンプライアンス マネージャー [で使用できるテンプレートの](compliance-manager-templates-list.md) 完全な一覧を表示します。

### <a name="purchase-premium-template-licenses"></a>プレミアム テンプレート ライセンスの購入

テンプレート ライセンスは、コンプライアンス マネージャーのライセンス契約に応じて、1 つ以上の方法で取得できます。 購入が完了すると、テンプレートは 48 時間以内にテナントで利用できます。

**商用およびGCC中程度**

商用アカウントGCC管理センターでテンプレート ライセンスを購入できます[(サブスクリプション](/microsoft-365/commerce/)、ライセンス、課金の詳細)。 購入するライセンスの数と支払いプランを選択します。

購入リンク:

- [商用](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/46E9BF2A-3C8D-4A69-A7E7-3DA04687636D)
- [GCCモデレート](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/3129986d-5f4b-413b-a34b-b706db5a7669)

また、プログラムまたはボリューム ライセンスへの参加を通クラウド ソリューション プロバイダー[ライセンス](https://partner.microsoft.com/membership/cloud-solution-provider)[を取得できます](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)。

**GCC高アカウントと DOD アカウント**

GCC高いアカウントと DOD アカウントは、ボリューム ライセンスを使用してテンプレート ライセンス[を購入する必要があります](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)。

### <a name="try-out-premium-templates"></a>プレミアム テンプレートを試す

購入前にプレミアム テンプレートを試す場合は、ライセンスの試用版を入手することもできます。 試用版ライセンスは、90 日間、最大 25 のテンプレートに対して良好です。 試用版ライセンスを取得すると、テンプレートは 48 時間以内にテナントで利用できます。

試用版を開始するには、組織の適切なリンクを選択します。

- [商用](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/e320704d-b7c9-4012-b6a6-0a2679790360)
- [GCCモデレート](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/87ed2908-0a8d-430a-9635-558ed42b581f)
- [GCC High](https://portal.office365.us/SubscriptionDetails?OfferId=e14362d7-2c11-4a43-9c92-59f1b499b96a)
- [DOD](https://portal.apps.mil/Commerce/Trial.aspx?OfferId=17e28290-7de6-41a9-af30-f6497396ab2e)

#### <a name="active-and-inactive-templates"></a>アクティブなテンプレートと非アクティブなテンプレート

テンプレートはアクティブまたは非アクティブとしてアクティブ状態を表示します。

- テンプレートは、そのテンプレート **から評価** を作成するとアクティブと見なされます。
- 組織が評価に **テンプレート** を使用しない場合、テンプレートは非アクティブと見なされます。

購入したプレミアム テンプレートに評価をリンクすると、そのテンプレートは 1 年間アクティブになります。 キャンセルしない限り、購入は自動的に更新されます。

また、プレミアム テンプレートを試用することもできます。 試用版ライセンスは、30 日間、最大 25 のテンプレートに対して良好です。 試用版が開始すると、テンプレートは 48 時間以内にテナントで利用できる必要があります。 試用版は、ライセンスを使用してアクティブ<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター。</a>

#### <a name="activated-templates-counter"></a>アクティブ化されたテンプレート カウンター

評価ページと評価テンプレート ページには、上部の **近くにアクティブ化されたテンプレート** カウンターがあります。 このカウンターには、ライセンス契約に従って使用する資格がある数の中で使用されているテンプレートの数が表示されます。 テンプレートの使用は、認定レベルでカウントされます。

たとえば、カウンターに 2/5 が表示されている場合、使用できる 5 つのテンプレートの中から 2 つのテンプレートがアクティブ化されています。

カウンターに 5/2 が表示されている場合は、組織が制限を超え、使用しているプレミアム テンプレートの 3 つを購入する必要があります。

Microsoft 365ユニバーサル バージョンのテンプレートには共同ライセンスが適用され、複数の製品で同じ基になる証明書を使用できます。 同じテンプレートのどちらかまたは両方のバージョンを使用すると、アクティブ化されたテンプレートは 1 つのみカウントされます。

詳細については、「コンプライアンス マネージャーの [ライセンス ガイダンス」を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)。

## <a name="view-and-manage-templates"></a>テンプレートの表示と管理

コンプライアンス マネージャーの [評価テンプレート] ページには、テンプレートの一覧と、テンプレートに関する主要な詳細が表示されます。 このリストには、コンプライアンス マネージャーが提供するテンプレートのほか、組織が変更または作成したテンプレートも含まれます。 フィルターを適用して、認定、製品範囲、国、業界、作成者、および評価の作成にテンプレートが有効になっているかどうかに基づいてテンプレートを検索できます。

行からテンプレートを選択して、詳細ページを表示します。 このページには、テンプレートの説明と、認定、スコープ、およびコントロールの詳細に関する詳細情報が含まれています。 このページでは、適切なボタンを選択して、評価の作成、テンプレート データのエクセルへのエクスポート、またはテンプレートの変更を行うことができます。

## <a name="create-an-assessment-template"></a>評価テンプレートの作成

コンプライアンス マネージャーでカスタム評価用の独自の新しいテンプレートを作成するには、特別に書式設定されたスプレッドシートExcelを使用して、必要なコントロール データを組み立てます。 スプレッドシートが完成すると、コンプライアンス マネージャーにインポートされます。 詳細については、「評価テンプレートの [作成」を参照してください](compliance-manager-templates-create.md)。

## <a name="modify-an-assessment-template"></a>評価テンプレートの変更

コンプライアンス マネージャーで評価を操作する場合は、作成した評価テンプレートを変更できます。 このプロセスは、テンプレートの作成プロセスと似ています。テンプレート データを含む書式設定されたExcelファイルをアップロードします。 変更を加える方法と、維持するデータを保持する方法の詳細については、「評価テンプレートの変更 [」を参照してください](compliance-manager-templates-modify.md)。

## <a name="extend-an-assessment-template"></a>評価テンプレートを拡張する

コンプライアンス マネージャーには、独自のコントロールと改善アクションを既存のテンプレートに追加するオプションがあります。 このプロセスは、テンプレートの拡張と呼ばれる。 テンプレートを拡張するには、評価テンプレートまたはユニバーサル評価テンプレートを拡張するかどうかに応じて、テンプレート データに追加する特別な手順Microsoft 365使用します。 詳細については、「評価テンプレートを [拡張する」を参照してください](compliance-manager-templates-extend.md)。

## <a name="format-assessment-template-data-in-excel"></a>評価テンプレート のデータの書式を設定Excel

コンプライアンス マネージャーで評価テンプレートを作成、変更、または拡張する場合は、特定の形式とスキーマを使用Excelスプレッドシートを使用します。 ファイルが正しくインポートされるようにするには、これらの仕様に従う必要があります。 詳細については、「評価テンプレート データ[の書式設定」を参照Excel。](compliance-manager-templates-format-excel.md)

## <a name="export-a-template"></a>テンプレートのエクスポート

テンプレートのすべてのデータをExcelファイルをエクスポートできます。 テンプレートを変更するには、変更プロセスで編集およびアップロードする Excelファイルになりますので、テンプレートをエクスポートする[必要があります](compliance-manager-templates-modify.md)。 新しいカスタム テンプレートの作成中にデータを使用する場合は、参照用にテンプレートをエクスポートすることもできます。

テンプレートをエクスポートするには、テンプレートの詳細ページに移動し、[テンプレートにエクスポート] ボタン **Excel** します。

コンプライアンス マネージャー テンプレートから拡張したテンプレートをエクスポートする場合、エクスポートされるファイルには、テンプレートに追加した属性だけが含まれます。 エクスポートされたファイルには、Microsoft が提供する元のテンプレート データは含めされません。 このようなレポートを取得するには、評価レポートをエクスポートする [手順を参照してください](compliance-manager-assessments.md#export-an-assessment-report)。