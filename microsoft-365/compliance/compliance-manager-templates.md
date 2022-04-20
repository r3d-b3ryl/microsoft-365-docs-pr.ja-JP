---
title: Microsoft Purview コンプライアンス マネージャーでの評価テンプレートの操作
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
description: Microsoft Purview コンプライアンス マネージャーで評価を構築するためのテンプレートを使用および管理する方法について説明します。 書式設定されたExcel ファイルを使用してテンプレートを作成および変更します。
ms.openlocfilehash: 009b2d742ab135abcde7c3ab73f9ec15c05c8f29
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64972785"
---
# <a name="learn-about-assessment-templates-in-compliance-manager"></a>コンプライアンス マネージャーの評価テンプレートについて学習する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

**この記事では、次の操作を行います。****テンプレートのしくみ** と、評価テンプレート ページから **テンプレートを管理する方法** について説明します。 新しいテンプレートの **作成**、既存のテンプレート **の拡張** と **変更**、**Excelを使用したテンプレート データの書式設定**、テンプレート レポートのエクスポートの手順を説明 **します**。

> [!IMPORTANT]
> 組織で使用できる評価テンプレートは、ライセンス契約によって異なります。 [詳細を確認します](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-compliance-manager)。

## <a name="templates-overview"></a>テンプレートの概要

テンプレートは、コンプライアンス マネージャーで評価を作成するためのコントロールのフレームワークです。 Microsoft の包括的なテンプレート セットは、組織がデータの収集と使用を管理する国、地域、および業界固有の要件に準拠するのに役立ちます。

## <a name="template-versions-microsoft-and-universal"></a>テンプレート バージョン: Microsoft とユニバーサル

テンプレートは、EU GDPR テンプレートや ISO/IEC 27701:2019 テンプレートなど、基になる認定または規制と同じ名前で参照されます。

コンプライアンス マネージャーは、さまざまな種類の製品を評価するために使用できます。 ベースライン以外のすべてのテンプレートには、定義済みの製品 (Microsoft 365など) に適用される少なくとも 1 つのバージョンと、他の製品に合わせて調整できるユニバーサル バージョンが用意されています。 ユニバーサル テンプレートからの評価は、より一般化されていますが、複数の製品にわたる組織のコンプライアンスを簡単に追跡するのに役立つため、柔軟性が広がっています。

米国政府Community (GCC) 中、GCC高、国防総省 (DoD) のお客様は、現在ユニバーサル テンプレートを使用できません。

## <a name="template-availability-and-licensing"></a>テンプレートの可用性とライセンス

コンプライアンス マネージャーには、含まれるテンプレートと Premium テンプレートの 2 つのカテゴリがあります。

1. **付属のテンプレート** は、コンプライアンス マネージャーのライセンスによって付与され、主要な規制と要件をカバーします。 ライセンス契約で使用できるテンプレートの詳細については、 [ライセンスの詳細を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)。
2. **追加** のニーズとシナリオをカバーするプレミアム テンプレートは、テンプレート ライセンスを購入することで取得できます。

評価の作成を開始すると、コンプライアンス マネージャーによってアクティブなテンプレートの数が追跡され、使用状況を監視できます。 詳細については、「 [アクティブなテンプレートと非アクティブなテンプレート](compliance-manager-templates.md#active-and-inactive-templates)」を参照してください。

コンプライアンス マネージャーで使用可能 [なテンプレートの完全な一覧](compliance-manager-templates-list.md) を表示します。

### <a name="purchase-premium-template-licenses"></a>Premium テンプレート ライセンスを購入する

テンプレート ライセンスは、コンプライアンス マネージャーのライセンス契約に応じて、これらの方法の 1 つ以上で取得できます。 購入が完了したら、48 時間以内にテナントでテンプレートを使用できるようになります。

**商用およびGCC中**

コマーシャル アカウントと GCC Moderate アカウントは、管理センターでテンプレート ライセンスを購入できます ([サブスクリプション、ライセンス、課金の詳細については、こちらを参照](/microsoft-365/commerce/)してください)。 購入するライセンスの数量と支払いプランを選択します。

購入リンク:

- [商用](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/46E9BF2A-3C8D-4A69-A7E7-3DA04687636D)
- [GCC 中](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/3129986d-5f4b-413b-a34b-b706db5a7669)

また、[クラウド ソリューション プロバイダー プログラム](https://partner.microsoft.com/membership/cloud-solution-provider)またはボリューム ライセンスへの参加を通じて[ライセンスを](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)取得することもできます。

**GCC High アカウントと DOD アカウント**

GCC High アカウントと DOD アカウントは、[ボリューム ライセンス](https://www.microsoft.com/licensing/licensing-programs/licensing-programs)を通じてテンプレート ライセンスを購入する必要があります。

### <a name="try-out-premium-templates"></a>Premium テンプレートを試す

購入する前に Premium テンプレートを試すには、ライセンスの試用版を入手することもできます。 試用版ライセンスは、90 日間、最大 25 個のテンプレートに適しています。 試用版ライセンスを取得すると、48 時間以内にテナントでテンプレートを使用できるようになります。

組織にコンプライアンス マネージャーの商用ライセンスがある場合は、「 [Microsoft Purview Compliance Manager Premium Assessments の無料試用版について](compliance-easy-trials-compliance-manager-assessments.md)」で試用版を開始する方法について説明します。

組織がGCCまたは DOD ライセンスの下にある場合は、組織に適した試用版のリンクを選択します。

- [GCC 中](https://admin.microsoft.com/Adminportal/Home?#/catalog/offer-details/compliance-manager-premium-assessment-add-on/87ed2908-0a8d-430a-9635-558ed42b581f)
- [GCC High](https://portal.office365.us/SubscriptionDetails?OfferId=e14362d7-2c11-4a43-9c92-59f1b499b96a)
- [DOD](https://portal.apps.mil/Commerce/Trial.aspx?OfferId=17e28290-7de6-41a9-af30-f6497396ab2e)

#### <a name="active-and-inactive-templates"></a>アクティブなテンプレートと非アクティブなテンプレート

テンプレートには、アクティブまたは非アクティブのいずれかのアクティブ化状態が表示されます。

- テンプレートは、そのテンプレートから評価を作成すると **アクティブ** と見なされます。
- 組織が評価に使用していない場合、テンプレートは **非アクティブ** と見なされます。

購入した Premium テンプレートに評価をリンクすると、そのテンプレートは 1 年間アクティブになります。 キャンセルしない限り、購入は自動的に更新されます。

#### <a name="activated-templates-counter"></a>アクティブ化されたテンプレート カウンター

評価ページと評価テンプレート ページには、上部付近に **アクティブ化されたテンプレート** カウンターがあります。 カウンターには、ライセンス契約に従って使用する資格のある数のうち、使用中のテンプレートの数が表示されます。 テンプレートの使用は、認定レベルでカウントされます。

たとえば、カウンターに 2/5 が表示されている場合は、組織が使用できる 5 つのテンプレートのうち 2 つのテンプレートをアクティブ化したことを意味します。

カウンターに 5/2 と表示されている場合は、組織がその制限を超え、使用中の Premium テンプレートの 3 つを購入する必要があることを示します。

Microsoft 365など、定義済みの製品のテンプレートには、同じテンプレートのユニバーサル バージョンとの共同ライセンスがあります。 これにより、複数の製品で同じ基になる認定を使用できます。 同じテンプレートの両方または両方のバージョンを使用すると、アクティブ化されたテンプレートは 1 つだけとしてカウントされます。

詳細については、 [コンプライアンス マネージャーのライセンスガイダンスに関するページを](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)参照してください。

## <a name="view-and-manage-templates"></a>テンプレートの表示と管理

コンプライアンス マネージャーの [評価テンプレート] ページには、テンプレートの一覧とそれらに関する重要な詳細が表示されます。 このリストには、コンプライアンス マネージャーが提供するテンプレートのほか、組織が変更または作成したテンプレートも含まれます。 フィルターを適用して、認定、製品スコープ、国、業界、それを作成したユーザー、およびテンプレートが評価作成に有効になっているかどうかを基にテンプレートを検索できます。

その行からテンプレートを選択して、詳細ページを表示します。 このページには、テンプレートの説明と、認定、スコープ、コントロールの詳細に関する詳細情報が含まれています。 このページでは、適切なボタンを選択して、評価の作成、テンプレート データのエクセルへのエクスポート、またはテンプレートの変更を行うことができます。

## <a name="create-an-assessment-template"></a>評価テンプレートを作成する

コンプライアンス マネージャーでカスタム評価用の独自の新しいテンプレートを作成するには、特別に書式設定されたExcel スプレッドシートを使用して、必要なコントロール データをアセンブルします。 スプレッドシートを完了すると、コンプライアンス マネージャーにインポートされます。 詳細については、「 [評価テンプレートの作成」を](compliance-manager-templates-create.md)参照してください。

## <a name="modify-an-assessment-template"></a>評価テンプレートを変更する

コンプライアンス マネージャーで評価を操作する場合は、作成した評価テンプレートを変更できます。 このプロセスは、書式設定されたExcel ファイルをテンプレート データと共にアップロードするという点で、テンプレート作成プロセスと似ています。 変更を加える方法と、維持するデータを保持する方法の詳細については、「 [評価テンプレートの変更」を](compliance-manager-templates-modify.md)参照してください。

## <a name="extend-an-assessment-template"></a>評価テンプレートを拡張する

コンプライアンス マネージャーには、独自のコントロールと改善アクションを既存のテンプレートに追加するオプションが用意されています。 このプロセスは、テンプレートの拡張と呼ばれます。 テンプレートを拡張するには、Microsoft 評価テンプレートとユニバーサル評価テンプレートのどちらを拡張するかに応じて、テンプレート データに追加するための特別な手順を使用します。 詳細については、「 [評価テンプレートの拡張」を](compliance-manager-templates-extend.md)参照してください。

## <a name="format-assessment-template-data-in-excel"></a>Excelでの評価テンプレート データの書式設定

コンプライアンス マネージャーで評価テンプレートを作成、変更、または拡張する場合は、特定の形式とスキーマを使用するExcelスプレッドシートを操作します。 ファイルを正しくインポートするには、これらの仕様に従う必要があります。 詳細については、「[Excelでの評価テンプレート データの書式設定](compliance-manager-templates-format-excel.md)」を参照してください。

## <a name="export-a-template"></a>テンプレートをエクスポートする

テンプレートのすべてのデータを含むExcel ファイルをエクスポートできます。 テンプレートを変更するには、変更[プロセス](compliance-manager-templates-modify.md)で編集およびアップロードするExcel ファイルであるため、テンプレートをエクスポートする必要があります。 新しいカスタム テンプレートの作成中にテンプレートからデータを使用する場合は、参照用にテンプレートをエクスポートすることもできます。

テンプレートをエクスポートするには、テンプレートの詳細ページに移動し、[**Excelにエクスポート**] ボタンを選択します。

コンプライアンス マネージャー テンプレートから拡張したテンプレートをエクスポートする場合、エクスポートされたファイルには、テンプレートに追加した属性のみが含まれます。 エクスポートされたファイルには、Microsoft によって提供された元のテンプレート データは含まれません。 このようなレポートを取得するには、 [評価レポートをエクスポートする手順を](compliance-manager-assessments.md#export-an-assessment-report)参照してください。
