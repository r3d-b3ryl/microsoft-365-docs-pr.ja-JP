---
title: Microsoft 365 Defender
description: Microsoft 365 Defender は、デバイス、ID、データ、アプリケーションを保護するように設計された連携された脅威保護ソリューションです
keywords: MMicrosoft 365 Defender の概要、サイバー セキュリティ、高度な永続的な脅威、エンタープライズ セキュリティ、デバイス、デバイス, ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な捜索
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
- m365solution-m365-defender
- m365solution-scenario
- m365solution-overview
ms.custom:
- admindeeplinkDEFENDER
- intro-overview
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c8df50c6970ed3404283d1911f884057e7db5747
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666880"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験しますか? [ラボ環境で評価](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)、または[運用でパイロット プロジェクトを実行](m365d-pilot.md?ocid=cx-evalpilot)することができます。
>

Microsoft 365 Defender は、エンドポイント、ID、メール、およびアプリケーション全体での検出、防止、調査、応答をネイティブに調整し、高度な攻撃に対する統合された保護を提供する、侵害の前後に対応した統合エンタープライズ防御スイートです。

統合された Microsoft 365 Defender ソリューションを使用すると、セキュリティ担当者は、これらの各製品が受け取る脅威シグナルを結合し、脅威の完全な範囲と影響 (環境に入った方法、影響を受ける内容、現在組織に与える影響) を判断できます。 Microsoft 365 Defender は、攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、およびユーザー ID を自己修復する自動アクションを実行します。

<center><h2>Microsoft 365 Defender サービス</center></h2>
<table><tr><td><center><b><a href="/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint"><b>Microsoft Defender for Endpoint</b></center></a></td>
<td><center><b><a href="/microsoft-365/security/office-365-security/overview"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="/defender-for-identity/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Defender for Identity</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender 対話型ガイド

この対話型ガイドでは Microsoft 365 Defender で組織を保護する方法について説明します。 Microsoft 365 Defender を使用して、セキュリティ 上のリスクを検出し、組織への攻撃を調査し、有害なアクティビティを自動的に防止する方法について説明します。

[対話型のガイドをチェックしてください](https://aka.ms/M365Defender-InteractiveGuide)

## <a name="microsoft-365-defender-protection"></a>Microsoft 365 Defender の保護 

Microsoft 365 Defender サービスは次の保護を行います。

- **Defender for Endpoint を使用するエンドポイント** - Defender for Endpointは、予防的保護、違反後の検出、自動調査、および対応のための統合エンドポイント プラットフォームです。
- **電子メールと Defender for Office 365 との協働** - Defender for Office 365 は、電子メール メッセージ、リンク (URL)、およびコラボレーション ツールによって引き起こされる悪意のある脅威から組織を保護します。
- **Defender for Identity と Azure Active Directory (Azure AD) Identity Protection との同一性** - Defender for Identity は、オンプレミスの Active Directory ドメイン サービス (AD DS) のシグナルを使用して、組織に対する高度な脅威、セキュリティの低下した ID、内部関係者の不正な行動を特定し、検出し、調査します。 Azure AD Identity Protection は、クラウドベースのAzure ADにおける ID ベースのリスクの検出と修復を自動化します。
- **Microsoft Defender for Cloud Apps を搭載したアプリケーション** - Microsoft Defender for Cloud Apps は、高度な可視性、強力なデータ制御、強化された脅威からの保護をクラウドアプリに提供する包括的なクロス SaaS ソリューションです。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww]

Microsoft 365 Defender の独自の製品間レイヤーは、個々のサービス コンポーネントを次の要素に拡張します。

- シグナル共有と自動化されたアクションを通じて、攻撃から保護し、サービス全体の防御的な対応を調整します。
- アラート、疑わしいイベント、影響を受ける資産に関するデータを "インシデント" に参加させることで、製品のアラート、動作、セキュリティ チームのコンテキスト全体にわたる攻撃の全容を説明します。
- 自動修復によって影響を受ける資産の自己復旧をトリガーすることで、侵害への対応を自動化します。
- セキュリティ チームがエンドポイントと Office データ全体で詳細かつ効果的な脅威ハンティングを実行できるようにします。

Microsoft 365 Defender ポータルが、製品間で関連するすべてのアラートを 1 つのインシデントに関連付ける方法の例を次に示します。

:::image type="content" source="../../media/overview-incident.png" alt-text="インシデントの概要ページ" lightbox="../../media/overview-incident.png":::

インシデントに関連するアラートの一覧の例を次に示します。

:::image type="content" source="../../media/incident-list.png" alt-text="インシデントのアラートの一覧" lightbox="../../media/incident-list.png":::

電子メールとエンドポイントの生データに基づくクエリベースのハンティングの例を次に示します。

:::image type="content" source="../../media/advanced-hunting.png" alt-text=" クエリの詳細を含む [高度なハンティング] ページ" lightbox="../../media/advanced-hunting.png":::

Microsoft 365 Defender クロスプロダクト機能には、次のようなものがあります。

- **Microsoft 365 Defender ポータルの製品間の単一ウィンドウ** - <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>の単一のキューとウィンドウでの検出、影響を受けた資産、実行された自動アクション、および関連する証拠に関するすべての情報の一元的なビュー。 
- **複合インシデント キュー** - セキュリティ担当者が、攻撃範囲全体、影響を受ける資産、自動修復アクションをグループ化し、適切なタイミングで表示できるようにすることで、重要な情報に集中できるようにします。 
- **脅威への自動対応** - Microsoft 365 Defender 製品間で重要な脅威情報がリアルタイムで共有され、攻撃の進行を阻止できます。 

   たとえば、Defender for Endpoint によって保護されているエンドポイントで悪意のあるファイルが検出された場合、Defender for Office 365 は、すべての電子メール メッセージからファイルをスキャンして削除するように指示します。 ファイルは、Microsoft 365 セキュリティ スイート全体によってブロックされます。

- **侵害されたデバイス、ユーザー ID、メールボックス** の自己復旧 - Microsoft 365 Defender では、AI を利用した自動アクションとプレイブックを使用して、影響を受けた資産をセキュリティで保護された状態に修復します。 Microsoft 365 Defender では、スイート製品の自動修復機能を利用して、インシデントに関連するすべての影響を受ける資産が可能な限り自動的に修復されるようにします。
- **製品間脅威ハンティング** - セキュリティ チームは、組織的知識を活用して、さまざまな保護製品によって収集された生データに対して独自のカスタム クエリを作成することで、侵害の兆候を探し出すことができます。 Microsoft 365 Defender は、エンドポイントと Defender for Office 365 データ全体で 30 日間の履歴の生信号とアラート データへのクエリ ベースのアクセスを提供します。

## <a name="get-started"></a>概要

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a> で Microsoft 365 Defender ポータルにてサービスを有効にするには、Microsoft 365 Defender のライセンス要件を満たす必要があります。詳細については、以下を参照してください。

- [ライセンス要件](prerequisites.md#licensing-requirements)
- [Microsoft 365 Defender を有効にする](m365d-enable.md)

## <a name="the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータル

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>は、*電子メール*、*コラボレーション*、*ID*、*デバイス*、*アプリ* の脅威に対する保護、検出、調査、対応を一元的な場所に組み合わせたものです。

この単一ウィンドウには、Microsoft 365 Defender ポータルや Office 365 セキュリティ/コンプライアンス センターなどの、既存の Microsoft セキュリティ ポータルの機能がまとめられています。 Microsoft 365 Defender ポータルは、情報への迅速なアクセス、よりシンプルなレイアウト、およびより簡単に使用できるように関連情報をまとめることを重視しています。 内容は以下のとおりです。

- **[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365 は、メールと Office 365 リソースを保護するための一連の防止、検出、調査、およびハンティング機能を使用して、組織が企業を保護するのに役立ちます。
- **[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** は、組織内のデバイスに対して、予防的な保護、侵害後の検出、自動調査、および対応を提供します。
- **[Microsoft 365 Defender](microsoft-365-defender.md)** は、Microsoft 365セキュリティ ポートフォリオを利用してドメイン間の脅威データを自動的に分析し、1 つのダッシュボードで攻撃の画像を作成する Microsoft *の拡張検出および応答* (XDR) ソリューションの一部です。
- **[Microsoft Defender for Cloud Apps](/cloud-app-security/)** は、包括的なクロス SaaS および PaaS ソリューションであり、クラウド アプリに対する詳細な可視性、強力なデータ制御、強化された脅威保護を実現します。

Office 365 セキュリティ/コンプライアンス センターまたは Microsoft 365 Defender ポータルからの変更点に関する情報が必要な場合は、以下を参照してください。

- [Microsoft 365 Defender の Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender の Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)

> [!NOTE]
> Microsoft 365 Defender ポータルは、既存のロールベースのアクセスを使用して適用し、各セキュリティ モデルを統合ポータルに移動します。 各収束ワークロードには、独自のロールベースのアクセス権があります。 製品に既に含まれているロールは、Microsoft 365 Defender ポータルに自動的に集約されます。 ただし、Microsoft Defender for Cloud Apps では引き続き独自のロールとアクセス許可が処理されます。

### <a name="what-to-expect"></a>想定される変化

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 セキュリティ/コンプライアンス センター</a>および Microsoft 365 セキュリティ センターで使用するすべてのセキュリティ コンテンツは、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で確認できるようになりました。

Microsoft 365 Defender ポータルは、さまざまなワークロードからのシグナルを一連の統合エクスペリエンスに取り込むことで、セキュリティ チームが攻撃を調査して対応する上で役立ちます。

- インシデントとアラート
- 検索
- アクション センター
- 脅威の分析

Microsoft 365 Defender は、Microsoft Defender for Office 365 および Microsoft Defender for Endpoint を統合する際に、*統一性、明確性、および共通の目標* を強調しています。 統合は、以下にリストされている優先順位に基づいており、各セキュリティ スイートが以下の組み合わせにもたらした機能を犠牲にすることなく行われました。

- 共通の構築ブロック
- 共通の用語
- 共通のエンティティ
- 他のワークロードと同等の機能

> [!NOTE]
> Microsoft 365 Defender ポータルにアクセスするのに、お客様が移行手順を実行したり、新しいライセンスを購入したりする必要はありません。 たとえば、この新しいポータルは、Microsoft Defender for Office 365 プラン 1 およびプラン 2 の場合と同様に、E3 サブスクリプションを持つ管理者がアクセスできます。ただし、Exchange Online Protection または Defender for Office 365 プラン 1 のお客様には、サブスクリプション ライセンスでサポートされているセキュリティ機能のみが表示されます。 ポータルの目的は、セキュリティを一元化することです。

### <a name="unified-investigations"></a>統一された調査

セキュリティ情報を一元化すると、Microsoft 365 全体でセキュリティ インシデントを調査するための単一の場所が作成されます。 主な例は、Microsoft 365 Defender のクイック起動時の **インシデントとアラート** の下の **インシデント** です。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="Microsoft 365 Defender ポータルの [インシデント] ページ" lightbox="../../media/converged-incidents-2.png.png":::

インシデント名を選択すると、セキュリティ情報の一元化の価値を示すページが表示されます。

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="Microsoft 365 Defender ポータルのインシデントの [概要] ページ" lightbox="../../media/converged-incident-info-3.png":::

インシデントのページの上部に、**[概要]**、**[アラート]**、**[デバイス]**、**[ユーザー]**、**[メールボックス]**、**[調査]**、**[証拠と応答]**、および **[グラフ]** タブが表示されます。 詳細については、これらのタブを選択してください。 たとえば、**[ユーザー]** タブには、集中型ワークロード (Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Cloud Apps) のユーザーと、オンプレミスの Active Directory Domain Services (AD DS)、Azure AD、サードパーティの ID プロバイダーなどのさまざまなソースの情報が表示されます。 詳細については、「[ユーザーを調査する](investigate-users.md)」を参照してください。

環境内のインシデントを確認し、これらのタブをドリルダウンし、さまざまな種類の脅威に対してインシデントに提供される情報にアクセスする方法の理解を実践します。

詳細については、「[Microsoft 365 Defender のインシデント](incidents-overview.md)」を参照してください。

### <a name="improved-processes"></a>改善されたプロセス

共通のコントロールとコンテンツは、同じ場所に表示されるか、データの 1 つのフィードにまとめられて、見つけやすくなります。たとえば、統一された設定などです。

#### <a name="unified-settings"></a>統一された設定

:::image type="content" source="../../media/converged-add-role-9.png" alt-text="Microsoft 365 Defender ポータルの [設定] ページ" lightbox="../../media/converged-add-role-9.png":::

#### <a name="permissions--roles"></a>アクセス許可と役割

:::image type="content" source="../../media/converged-roles-5.png" alt-text="[アクセス許可&ロール] ページに表示されるエンドポイント ロール&グループ" lightbox="../../media/converged-roles-5.png":::

Microsoft 365 Defender へのアクセスは、Azure AD グローバル ロールまたはカスタム ロールを使用して構成されます。 Defender for Endpoint については、「[Microsoft 365 Defender ポータルにユーザー アクセスを割り当てる](/microsoft-365/security/defender-endpoint/assign-portal-access)」を参照してください。 Defender for Office 365 については、「[Microsoft 365 コンプライアンス センターと Microsoft 365 Defender のアクセス許可](../office-365-security/permissions-microsoft-365-compliance-security.md)」をご覧ください。

- [Microsoft 365 Defender へのアクセスを管理する](m365d-permissions.md)方法の詳細
- Microsoft 365 Defender で[カスタム ロールを作成](custom-roles.md)する方法の詳細

> [!NOTE]
> Microsoft 365 Defender の Microsoft Defender for Endpoint では、[Microsoft 365 Defender ポータルでのアクセスの許可](./mssp-access.md)と同じ方法で、[マネージド セキュリティ サービス プロバイダー (MSSP) へのアクセスの許可](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)をサポートしています。

#### <a name="integrated-reports"></a>統合レポート

レポートは、Microsoft 365 Defender でも統合されます。 管理者は、一般的なセキュリティ レポートから始めて、エンドポイント、メール、コラボレーションに関する特定のレポートに分岐できます。 ここでのリンクは、ワークロード構成に基づいて動的に生成されます。

#### <a name="quickly-view-your-microsoft-365-environment"></a>Microsoft 365 環境をすばやく表示する

**ホーム** ページには、セキュリティ チームが必要とする一般的なカードの多くが表示されます。 カードとデータの構成は、ユーザーの役割によって異なります。 Microsoft 365 Defender ポータルは役割ベースのアクセス制御を使用しているため、役割が異なれば、日常業務にとってより意味のあるカードが表示されます。

この一目でわかる情報は、組織内の最新の活動についていくのに役立ちます。 Microsoft 365 Defender は、さまざまなソースからの信号をまとめて、Microsoft 365 環境の全体像を示します。

カードは次のカテゴリに分類されます。

- **ID** - 組織内の ID を監視し、疑わしいまたは危険な行動を追跡します。[ID 保護の詳細情報](/azure/active-directory/identity-protection/overview-identity-protection)。
- **データ** - 無許可のデータ開示につながる可能性のあるユーザー アクティビティを追跡するのに役立ちます。
- **デバイス** - デバイス上のアラート、違反アクティビティ、およびその他の脅威に関する最新情報を取得します。
- **アプリ** - 組織でクラウド アプリがどのように使用されているかについての分析情報を得ます。 [Defender for Cloud Apps で検出されたアプリの詳細情報](/cloud-app-security/discovered-apps)。


#### <a name="search-across-entities-preview"></a>エンティティ間の検索 (プレビュー)

>[!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。
検索バーはページの上部にあります。 入力すると、エンティティを見つけやすくするための提案が提供されます。 強化された検索結果ページでは、すべてのエンティティからの結果が一元化されます。

Defender for Endpoint と Defender for Identity では、次のエンティティを検索できます。 

- **デバイス** - Defender for Endpoint と Defender for Identity の両方でサポートされます。 検索演算子の使用をサポートします。 
- **ユーザー** - Defender for Endpoint、Defender for Identity、Defender for Cloud Apps でサポートされています。 
- **ファイル、IP、URL** - Defender for Endpoint と同じ機能。

    >[!NOTE]
    >IP 検索と URL 検索は完全に一致し、検索結果ページには表示されません。エンティティ ページに直接移動します。 

- **TVM** - Defender for Endpoint と同じ機能 (脆弱性、ソフトウェア、推奨事項)。 

 





### <a name="threat-analytics-with-better-data-coverage"></a>より優れたデータ カバレッジを備えた脅威の分析

次の Microsoft 365 Defender 脅威分析統合エクスペリエンスを使用して、新たな脅威を追跡し、対応します。

- Microsoft Defender for Endpoint と Microsoft Defender for Office 365 の間のデータ カバレッジが向上し、インシデント管理、自動調査、修復、およびドメイン全体での予防的または事後対応的な脅威ハンティングの組み合わせが可能になります。
- Microsoft Defender for Endpoint から既に利用可能なエンドポイント データに加えて、Microsoft Defender for Office 365 からのメール関連の検出と軽減。
- Microsoft Defender for Endpoint と Microsoft Defender for Office 365 全体のエンドツーエンドの攻撃ストーリーにアラートを集約して、作業キューを削減し、調査を簡素化および高速化する、脅威関連のインシデントのビュー。
- Microsoft 365 Defender ソリューションによって検出され、ブロックされた攻撃の試み。 さらなる曝露のリスクを軽減し、回復力を高める予防措置を推進するために使用できるデータもあります。
- 実用的な情報にスポットライトを当て、緊急に焦点を合わせ、調査し、レポートから活用するデータをすばやく特定できるようにする拡張された設計。

### <a name="a-centralized-learning-hub"></a>一元化されたラーニング ハブ

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>には、Microsoft セキュリティ ブログ、YouTube の Microsoft セキュリティ コミュニティ、docs.microsoft.com の公式ドキュメントなどのリソースから公式ガイダンスを作成するラーニング ハブが含まれています。

ラーニング ハブ内では、メールとコラボレーション (Microsoft Defender for Office 365) のガイダンスが、Endpoint (Microsoft Defender for Endpoint) および Microsoft 365 Defender ラーニング リソースと並んでいます。

ラーニング ハブは、「Microsoft 365 Defenderを使用して調査する方法」などのトピックを中心に整理されたラーニング パスで開きます。 と "Microsoft Defender for Office 365ベスト プラクティス"。 このセクションは現在、Microsoft 内のセキュリティ製品グループによってキュレーションされています。 各ラーニング パスは、概念を理解するのにかかると予想される時間を反映しています。 たとえば、「Microsoft Defender for Office 365 ユーザー アカウントが侵害された場合の手順」は 8 分かかると予想されており、その場で学ぶ価値があります。

コンテンツをクリックした後、このサイトをブックマークして、ブックマークを 'セキュリティ' または 'クリティカル' フォルダーに整理すると便利な場合があります。 すべてのラーニング パスを表示するには、メイン パネルの [すべて表示] リンクをクリックします。

> [!NOTE]
> Microsoft 365 Defender のラーニング ハブの上部には、製品 (現在、Microsoft 365 Defender、Microsoft Defender for Endpoint、および Microsoft Defender for Office 365) から選択できる便利な **フィルター** があります。 各セクションの学習リソースの数がリストされていることに注意してください。これは、学習者がトレーニングと学習のために手元にあるリソースの数を追跡するのに役立ちます。
>
> 製品フィルターに沿って、現在のトピック、リソースの種類 (ビデオからウェビナーまで)、セキュリティ領域に関する知識または経験のレベル、セキュリティの役割、および製品の機能が一覧表示されます。

> [!TIP]
> [Microsoft Learn](/learn/) には、他にも多くの学習機会があります。 [コース MS-500T02-A: Microsoft 365 脅威に対する保護の実装](/learn/certifications/courses/ms-500t02)などといった認定トレーニングがあります。

### <a name="send-us-your-feedback"></a>フィードバックの送信

フィードバックをお寄せください。 私たちは常に改善を目指しているので、ご希望の内容がある場合は、[このビデオを視聴して、なぜ私たちが本当にフィードバックを読んでいると分かるのか](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)をご確認ください。

この記事からフィードバックを残すこともできます。[フィードバックの送信と表示] の下の最後にある [フィードバック] セクションのオプションは、*[この製品]*、または *[このページ]* です。

*製品* のフィードバックには、**[この製品]** ボタンを使用してください。

1. 記事の下部にある *[この製品]* を選択します。
    1. これらの指示を読み続ける場合は、ボタンを右クリックして [新しいタブで開く] を選択してください。
2. これにより、**UserVoice フォーラム** に移動します。
3. 2 つのオプションがあります。
    1. テキスト ボックス「*Office 365 でコンプライアンスを改善したり、ユーザーをより適切に保護するにはどうすればよいですか?*」まで下にスクロールして、*Microsoft 365 Defender* に貼り付けます。 結果から自分のようなアイデアを探して賛成票を投じるか、**[新しいアイデアを投稿する]** ボタンを使用できます。
    1. この問題がすでに報告されていると確信し、1 票または複数の票でそのプロファイルを上げたい場合は、UserVoice の右側にある *[フィードバックの送信]* ボックスを使用してください。 ｊい *Microsoft 365 Defender* を検索して、**問題を見つけ、投票ボタンを使用** して、その状態を引き上げます。

記事自体に関するフィードバックは、*[このページ]* を使用してください。 フィードバックしていただき、ありがとうございます。 あなたの声は製品の改善に役立ちます。

### <a name="explore-what-the-microsoft-365-defender-portal-has-to-offer"></a>Microsoft 365 Defender ポータルで提供される内容を確認する

Microsoft 365 Defender の機能を引き続き確認します。

- [インシデントとアラートを管理する](manage-incidents.md)
- [脅威の分析を使用して、新たな脅威を追跡し対応する](threat-analytics.md)
- [アクション センター](m365d-action-center.md)
- [デバイス、メール、アプリ、ID 全体の脅威を探す](./advanced-hunting-query-emails-devices.md)
- [カスタム検出ルール](./custom-detection-rules.md)
- [メールとコラボレーションのアラート](../../compliance/alert-policies.md#default-alert-policies)
- [フィッシング攻撃のシミュレーションを作成し](../office-365-security/attack-simulation-training.md)、[チームをトレーニングするためのペイロードを作成する](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)

## <a name="training-for-security-analysts"></a>セキュリティ アナリスト向けトレーニング

Microsoft Learn からのこのラーニング パスを使用すると、Microsoft 365 Defender と、それがセキュリティ上の脅威を特定、制御、修復するのにどのように役立つかを理解できます。

|トレーニング: |Microsoft 365 Defender を使用してサイバー攻撃を検出して対応する|
|---|---|
|![Microsoft 365 Defender トレーニング アイコン。](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Microsoft 365 Defender では、エンドポイント、ID、メール、アプリケーション間で脅威信号を統合し、巧妙なサイバー攻撃を包括的に保護することができます。 Microsoft 365 Defender は、インシデントを調査して対応し、継続的な悪意のあるサイバー セキュリティ活動を積極的に検索することができる中心的な環境です。<p> 1 時間 38 分 - ラーニング パス - 5 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/paths/defender-detect-respond/)


## <a name="see-also"></a>関連項目

- [Microsoft 365 Defender の新機能](whats-new.md)
- [Microsoft 365 Defender の Microsoft Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender の Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
