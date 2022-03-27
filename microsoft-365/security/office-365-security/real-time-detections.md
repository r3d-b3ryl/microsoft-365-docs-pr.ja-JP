---
title: Microsoft Defender の脅威エクスプローラーとリアルタイム検出の基本Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: エクスプローラーまたはリアルタイム検出を使用して、脅威を効率的に調査して対応します。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3b889649de7b56d6a1b5300ff323850a4e555b57
ms.sourcegitcommit: 9c8eca862a2f0fdca7a66c641e382e37fcaefa10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2022
ms.locfileid: "63775364"
---
# <a name="explorer-and-real-time-detections"></a>エクスプローラーとリアルタイムの検出

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

この記事の内容:

- [エクスプローラーとリアルタイムの検出の違い](#differences-between-explorer-and-real-time-detections)
- [エクスプローラーとリアルタイム検出のエクスペリエンスの更新](#updated-experience-for-explorer-and-real-time-detections)
- [必要なライセンスとアクセス許可](#required-licenses-and-permissions)

> [!NOTE]
> これは、**エクスプローラー (** 脅威エクスプローラーとも呼ばれる)、電子メール セキュリティ、**エクスプローラー** とリアルタイム検出の基本 (ツールの違い、操作に必要なアクセス許可など) の **3** 記事シリーズの一部です。 このシリーズの他の 2 つの記事は、 [Explorer での脅威](threat-hunting-in-threat-explorer.md) の検出とエクスプローラー [のメール セキュリティです](email-security-in-microsoft-defender.md)。

この記事では、エクスプローラーとリアルタイム検出レポートの違い、エクスプローラーでの更新されたエクスペリエンス、新しいエクスペリエンスと新しいエクスペリエンスを切り替えるリアルタイム検出、および必要なライセンスとアクセス許可について説明します。

[組織が microsoft Defender for Office 365](defender-for-office-365.md) を持ち、アクセス許可を持っている [](#required-licenses-and-permissions)場合は、**エクスプローラー (脅威****エクスプローラーとも呼** ばれる) またはリアルタイム検出を使用して、脅威を検出して修復できます。

[電子メール Microsoft 365 Defender] <https://security.microsoft.com>の [電子メール &**]** に移動し、[**エクスプローラー**] または [リアルタイム検出 **] を選択します**。 ページに直接移動するには、またはを使用 <https://security.microsoft.com/threatexplorer> します <https://security.microsoft.com/realtimereports>。

これらのツールで以下のことができます。

- セキュリティ機能によって検出されたマルウェアMicrosoft 365参照してください。
- フィッシング URL を表示し、[評決データ] をクリックします。
- エクスプローラーでビューから自動調査と応答プロセスを開始します。
- 悪意のあるメールなどについて調査します。

詳細については、「Explorer を使用した [メール セキュリティ」を参照してください](email-security-in-microsoft-defender.md)。

## <a name="differences-between-explorer-and-real-time-detections"></a>エクスプローラーとリアルタイムの検出の違い

- *リアルタイム検出は、* Defender でプラン 1 で使用できるレポート Office 365ツールです。 *Threat Explorer* は、Defender で利用可能な脅威の検出と修復ツールで、Office 365 2 です。
- リアルタイム検出レポートを使用すると、リアルタイムで検出を表示できます。 脅威エクスプローラーも同様にこれを行いますが、攻撃キャンペーンの強調表示など、特定の攻撃に関する追加の詳細を提供し、セキュリティ運用チームに脅威を修復する機能 (自動調査と応答[](automated-investigation-response-office.md)調査のトリガーを含む) を提供します。
- すべての *電子メール ビュー* は脅威エクスプローラーで使用できますが、リアルタイム検出レポートには含まれません。
- 豊富なフィルター機能と修復アクションは、Threat Explorer に含まれています。 詳細については、「[Microsoft Defender for Office 365 サービスの説明:](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) Defender 全体の機能可用性」を参照Office 365してください。

## <a name="updated-experience-for-explorer-and-real-time-detections"></a>エクスプローラーとリアルタイム検出のエクスペリエンスの更新

脅威エクスプローラーとリアルタイム検出のエクスペリエンスは、最新のアクセシビリティ標準に合わせて更新され、ワークフローを最適化します。 しばらくの間、古いエクスペリエンスと新しいエクスペリエンスを切り替えできます。  

> [!NOTE]
> 切り取りはアカウントにのみ影響を与え、テナント内の他のユーザーには影響しません。 

脅威エクスプローラーとリアルタイム検出は、次のビューに分かれています。

- *すべてのメール*: Defender for office 365 で分析されたすべてのメールを表示し、良いメールと悪意のあるメールの両方が含まれている。 この機能は Threat Explorer にのみ存在し、リアルタイム検出には使用できません。 既定では、2 日間のデータが表示され、最大 30 日間まで拡張できます。 これは、脅威エクスプローラーの既定のビューです。  

- *マルウェア ビュー*: マルウェアの脅威が特定された電子メールを表示します。 これはリアルタイム検出の既定のビューで、2 日間のデータを表示します (30 日間に拡張できます)。  

- *フィッシング ビュー*: フィッシング脅威が識別されたメールを表示します。

- *コンテンツ マルウェア ビュー*: ファイル間で共有されるファイルで識別される悪意のある検出OneDrive、SharePoint、またはTeams。 

これらのエクスペリエンスの一般的なコンポーネントを次に示します。

- フィルター

    - さまざまなフィルターを使用して、電子メールまたはファイルの属性に基づいてデータを表示できます。  

    - 既定では、時間フィルターはレコードに適用され、2 日間適用されます。  

    - 複数のフィルターを適用する場合、それらは 'AND' モードで適用され、高度なフィルターを使用して 'OR' モードに変更できます。  

    - コンマを使用して、同じフィルターに複数の値を追加できます。  

    > [!div class="mx-imgBorder"]
    > ![エクスプローラー フィルター](../../media/explorer-new-experience-filters.png)

- グラフ

    - グラフは、フィルターに基づくデータの視覚的な集計ビューを提供します。 さまざまなフィルターを使用して、異なる次元でデータを表示できます。  

    > [!NOTE]
    > リスト ビューにエントリが表示されている場合でも、グラフ ビューに結果が表示されません。 これは、フィルターがデータを生成しない場合に発生します。 たとえば、フィルター マルウェア ファミリを適用したが、基になるデータに悪意のあるメールがない場合、このシナリオで使用できるデータがないというメッセージが表示されることがあります。  

    > [!div class="mx-imgBorder"]
    > ![エクスプローラー のグラフ ビュー](../../media/explorer-new-experience-export-chart-data.png)

- 結果グリッド  

    - 結果グリッドには、適用したフィルターに基づいて電子メールの結果が表示されます。  

    - テナントの構成セットに基づいて、データは UTC またはローカルタイム ゾーンで表示され、タイム ゾーン情報は最初の列に表示されます。  

    - [新しいウィンドウで開く] アイコンをクリックすると、リスト ビューから個々の電子メール エンティティ ページ **に移動** できます。 

    - 列をカスタマイズして、ビューを最適化するために列を追加または削除することもできます。

    > [!Note]
    > グラフ ビューと *リスト ビューを* 切り替 *え、* 結果セットを最大化できます。  

    > [!div class="mx-imgBorder"]
    > ![エクスプローラー のグリッド ビュー](../../media/explorer-new-experience-list-chart-view.png)

- 詳細なフライアウト  

    - ハイパーリンクをクリックすると、電子メールの概要パネル ([件名] 列のエントリ)、受信者、または IP フライアウトにアクセスできます。  

    - 電子メールの概要パネルは、従来の電子メール の飛び出しを置き換え、電子メール エンティティ パネルにアクセスするパスも提供します。  

    - IP、受信者、URL など、個々のエンティティ のフライアウトは同じ情報を反映しますが、単一のタブ ベースのビューに表示され、要件に基づいてさまざまなセクションを展開および折りたたみできます。  

    - URL などのフライアウトの場合は、[すべてのメールの表示] または [すべてのクリック数の表示] をクリックして、その URL を含むメール/クリックの完全なセットを表示し、結果セットをエクスポートできます。  

- Actions

    - 脅威エクスプローラーから、[メールの削除] のような修復 *アクションをトリガーできます*。 修復、修復の制限、および追跡修復の詳細については、「悪意のある電子メールの修復 [」を参照してください](remediate-malicious-email-delivered-office-365.md)。  

- エクスポート

    - [グラフ データの **エクスポート] をクリックすると** 、グラフの詳細をエクスポートできます。 同様に、[電子メール リスト **のエクスポート] をクリックして** メールの詳細をエクスポートします。

    - メール リストには最大 200K のレコードをエクスポートできます。 ただし、システムのパフォーマンスを向上し、ダウンロード時間を短縮するには、さまざまな電子メール フィルターを使用する必要があります。

    > [!div class="mx-imgBorder"]
    > ![グラフ データのエクスポート](../../media/explorer-new-experience-export-chart-data.png)

これらの機能に加えて、トップ URL、トップ クリック、トップ ターゲット ユーザー、メール配信元など、更新されたエクスペリエンスも *取得できます*。 *エクスプローラー内で適用**する* フィルターに基づいて、上位 URL、トップ クリック数、および上位対象ユーザーをさらにフィルター処理できます。 

## <a name="required-licenses-and-permissions"></a>必要なライセンスとアクセス許可

エクスプローラーまたは[リアルタイム検出のいずれかをOffice 365](defender-for-office-365.md)するには、Microsoft Defender が必要です。

- エクスプローラーは、プラン 2 の Defender にのみOffice 365されます。
- リアルタイム検出レポートは、Defender for Office 365プラン 1 に含まれています。

セキュリティ運用チームは、Office 365 の Defender によって保護される必要があるすべてのユーザーにライセンスを割り当て、エクスプローラーとリアルタイムの検出では、ライセンスを持つユーザーの検出データが表示される点に注意する必要があります。

エクスプローラーまたはリアルタイム検出を *表示* および使用するには、次のアクセス許可が必要です。

- [Defender for Office 365:
  - 組織管理
  - セキュリティ管理者 (この管理者は、管理者センター Azure Active Directory割り当てることができます (<https://aad.portal.azure.com>)
  - セキュリティ閲覧者
- このExchange Online:
  - 組織の管理
  - 表示専用組織の管理
  - "View-Only Recipients/表示専用受信者"
  - コンプライアンス管理

役割とアクセス許可の詳細については、次の記事を参照してください。

- [Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)
- [Exchange Online のアクセス許可](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a>詳細情報

- [脅威エクスプローラーは、電子メール エンティティ ページで電子メールの詳細を収集します。](mdo-email-entity-page.md)
- [配信された悪意のあるメールの検索と調査](investigate-malicious-email-that-was-delivered.md)
- [オンライン、オンライン、SharePoint、およびOneDriveで検出された悪意のあるMicrosoft Teams](mdo-for-spo-odb-and-teams.md)
- [脅威保護の状態レポート](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft Threat Protection での自動調査および対応](automated-investigation-response-office.md)
