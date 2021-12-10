---
title: Microsoft 365 Defender
description: Microsoft 365 Defenderは、デバイス、ID、データ、アプリケーションを保護するように設計された協調脅威保護ソリューションです。
keywords: MMicrosoft 365 Defender の概要、サイバーセキュリティ、高度な永続的脅威、エンタープライズ セキュリティ、デバイス、デバイス、ID、ユーザー、データ、アプリケーション、インシデント、自動調査と修復、高度な検出
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1d9c21b68de920b18ec5941eec7c093a64a06023
ms.sourcegitcommit: e246725b0935067aad886530d5178972c0f895d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2021
ms.locfileid: "61401404"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験しますか? [ラボ環境で評価](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)、または[運用でパイロット プロジェクトを実行](m365d-pilot.md?ocid=cx-evalpilot)することができます。
>

Microsoft 365 Defender は、エンドポイント、ID、メール、およびアプリケーション全体での検出、防止、調査、応答をネイティブに調整し、高度な攻撃に対する統合された保護を提供する、侵害の前後に対応した統合エンタープライズ防御スイートです。

統合された Microsoft 365 Defender ソリューションを使用すると、セキュリティ専門家は、これらの各製品が受け取る脅威信号を一緒にまとめ、脅威の全範囲と影響、環境への入り方、影響を受ける状況、組織に対する現在の影響を判断できます。 Microsoft 365 Defender攻撃を防止または停止し、影響を受けるメールボックス、エンドポイント、およびユーザー ID を自己回復する自動アクションを実行します。

<center><h2>Microsoft 365 Defender サービス</center></h2>
<table><tr><td><center><b><a href="/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint"><b>エンドポイント用 Microsoft Defender</b></center></a></td>
<td><center><b><a href="/microsoft-365/security/office-365-security/overview"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="/defender-for-identity/"><b>Microsoft Defender for Identity</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Defender for Cloud Apps</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defenderガイド

この対話型ガイドでは、組織をセキュリティで保護する方法についてMicrosoft 365 Defender。 セキュリティ リスクの検出、Microsoft 365 Defender攻撃の調査、有害なアクティビティの自動防止に役立つ情報が表示されます。

[対話型のガイドをチェックしてください](https://aka.ms/M365Defender-InteractiveGuide)

## <a name="microsoft-365-defender-protection"></a>Microsoft 365 Defender保護

Microsoft 365 Defenderサービスは次の保護を行います。

- **Defender for Endpoint** を使用するエンドポイント - Defender for Endpoint は、予防保護、侵害後の検出、自動調査、および対応のための統合エンドポイント プラットフォームです。
- **Defender for Office 365 との** 電子メールとコラボレーション - Office 365 Defender は、電子メール メッセージ、リンク (URL)、およびコラボレーション ツールによる悪意のある脅威から組織を保護します。
- Defender for Identity と **Azure Active Directory Azure AD (Azure AD)** Identity Protection を持つ ID - Defender for Identity は、組織に向けられた高度な脅威、侵害された ID、悪意のあるインサイダーアクションを特定、検出、および調査するために、オンプレミスの Active Directory ドメイン サービス (AD DS) シグナルを使用します。 Azure AD Id Protection は、クラウド ベースのセキュリティ ポリシーで ID ベースのリスクの検出と修復を自動化Azure AD。
- **Microsoft Defender for Cloud Apps** を使用するアプリケーション - Microsoft Defender for Cloud Apps は、クラウド アプリに深い可視性、強力なデータ制御、強化された脅威保護をもたらす包括的なクロス SaaS ソリューションです。

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww]

Microsoft 365 Defender固有のクロスプロダクト 層は、個々のサービス コンポーネントを次の機能に拡張します。

- 信号の共有と自動化されたアクションを通じて、攻撃から保護し、サービス全体の防御応答を調整するのに役立ちます。
- アラート、疑わしいイベント、影響を受けた資産に関するデータを 「インシデント」 に参加することで、セキュリティ チームの製品アラート、動作、コンテキスト全体にわたる攻撃の全ストーリーを説明します。
- 影響を受け取ったアセットの自己修復を自動修復によってトリガーすることで、侵害への対応を自動化します。
- セキュリティ チームは、エンドポイント全体で詳細かつ効果的な脅威検出を実行し、データOfficeできます。

このポータルで、製品間のすべての関連Microsoft 365 Defender 1 つのインシデントに関連付ける方法の例を次に示します。

:::image type="content" source="../../media/overview-incident.png" alt-text="インシデントの概要ページの例" lightbox="../../media/overview-incident.png":::

インシデントに関連するアラートの一覧の例を次に示します。

:::image type="content" source="../../media/incident-list.png" alt-text="インシデントのアラートの一覧の例" lightbox="../../media/incident-list.png":::

電子メールとエンドポイントの生データの上にクエリ ベースの検索の例を示します。

:::image type="content" source="../../media/advanced-hunting.png" alt-text="高度な検索とクエリの例" lightbox="../../media/advanced-hunting.png":::

Microsoft 365 Defender機能には、次のものが含まれます。

- **Microsoft 365 Defender** ポータルのクロスプロダクト 単一ウィンドウ - Microsoft 365 Defender ポータルの 1 つのキューと 1 つのウィンドウ内の検出、影響を受けるアセット、自動アクション、および関連する <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"></a>証拠に関するすべての情報の中央ビューです。 
- **複合インシデント** キュー - セキュリティ専門家が攻撃範囲全体を確保することで重要な作業に集中するために、影響を受けたアセットと自動修復アクションがグループ化され、適切な時期に表示されます。 
- **脅威への自動対応**- 重大な脅威情報は、攻撃の進行を停止するために、Microsoft 365 Defender製品間でリアルタイムで共有されます。 

   たとえば、Defender for Endpoint によって保護されたエンドポイントで悪意のあるファイルが検出された場合、すべての電子メール メッセージからファイルをスキャンして削除するよう Defender に Office 365 に指示します。 このファイルは、セキュリティ スイート全体によってMicrosoft 365されます。

- **侵害されたデバイス**、ユーザー ID、メールボックスの自己修復 - Microsoft 365 Defender は、AI による自動アクションとプレイブックを使用して、影響を受け取ったアセットを安全な状態に戻します。 Microsoft 365 Defenderスイート製品の自動修復機能を活用して、インシデントに関連する影響を受けたすべての資産を可能な限り自動的に修復します。
- **製品間の脅威** の検出 - セキュリティ チームは、独自の組織の知識を活用して、さまざまな保護製品によって収集された生データに対して独自のカスタム クエリを作成することで、侵害の兆候を探し出します。 Microsoft 365 Defenderは、30 日間の過去の生信号と、エンドポイントと Defender 全体のアラート データへのクエリ ベースのアクセスを提供し、データOffice 365します。

## <a name="get-started"></a>作業の開始

Microsoft 365 Defender Microsoft 365 Defenderポータルでサービスを有効にする前に、Microsoft 365 Defender要件を満たす必要があります。詳細については、以下を <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a> 参照してください。

- [ライセンス要件](prerequisites.md#licensing-requirements)
- [Microsoft 365 Defender を有効にする](m365d-enable.md)

## <a name="the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータル

この <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderは</a>、電子メール、コラボレーション *、ID、* デバイス、アプリの脅威に対する保護、検出、調査、応答を一元的に組み合わせたものになります。 

この単一ウィンドウのガラスは、Microsoft 365 Defender ポータルやコンプライアンス センターの Office 365 セキュリティ &など、既存の Microsoft セキュリティ ポータルの機能を統合します。 このMicrosoft 365 Defenderポータルでは、情報への迅速なアクセス、レイアウトの簡易性、および関連情報のまとめが強調され、使いやすくなっています。 内容は以下のとおりです。

- **[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365 は、メールと Office 365 リソースを保護するための一連の防止、検出、調査、およびハンティング機能を使用して、組織が企業を保護するのに役立ちます。
- **[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** は、組織内のデバイスに対して、予防的な保護、侵害後の検出、自動調査、および対応を提供します。
- **[Microsoft 365 Defender](microsoft-365-defender.md)** は、Microsoft の *Extended Detection and Response* (XDR) ソリューションの一部であり、Microsoft 365 セキュリティ ポートフォリオを活用して、ドメイン全体の脅威データを自動的に分析し、単一のダッシュボードで攻撃の全体像を構築します。
- **[Microsoft Defender for Cloud Apps](/cloud-app-security/)** は、クラウド アプリに対する深い可視性、強力なデータ制御、強化された脅威保護をもたらす包括的なクロス SaaS および PaaS ソリューションです。

Office 365 セキュリティ センターまたはコンプライアンス センターまたは &ポータルからMicrosoft 365 Defender情報が必要な場合は、以下を参照してください。

- [Microsoft 365 Defender の Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender の Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)

> [!NOTE]
> このMicrosoft 365 Defenderは、既存の役割ベースのアクセスを使用して適用し、各セキュリティ モデルを統合ポータルに移動します。 各コンバージド ワークロードには、独自のロール ベースのアクセス権があります。 製品に既に存在する役割は、自動的にポータルのMicrosoft 365 Defenderされます。 ただし、Microsoft Defender for Cloud Apps は、独自の役割とアクセス許可を引き続き処理します。

### <a name="what-to-expect"></a>想定される変化

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077143" target="_blank">Office 365 セキュリティ</a>& コンプライアンス センターと Microsoft 365 セキュリティ センターで使用するセキュリティ コンテンツはすべて、Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">ポータルにあります</a>。

このMicrosoft 365 Defenderは、さまざまなワークロードからのシグナルを一連の統合エクスペリエンスに取り込み、セキュリティ チームが攻撃を調査して対応するのに役立ちます。

- インシデントとアラート
- 検索
- アクション センター
- 脅威の分析

Microsoft 365 Defender、Microsoft Defender  for microsoft Defender for Office 365エンドポイントを統合する場合、統一、明快さ、共通の目標を強調しています。 マージは、以下に示す優先順位に基づいて行われたので、各セキュリティ スイートが次の組み合わせに持ち込んだ機能を犠牲にすることなく行いました。

- 共通の構成要素
- 一般的な用語
- 共通エンティティ
- 他のワークロードとの機能のパリティ

> [!NOTE]
> 移行Microsoft 365 Defender移行手順を実行したり、新しいライセンスを購入したりすることなく、ポータルにアクセスできます。 たとえば、この新しいポータルは、Microsoft Defender for Office 365 Plan 1 および Plan 2 の場合と同様に、E3 サブスクリプションを持つ管理者がアクセスできます。ただし、Exchange Online Protection または Defender for Office 365 Plan 1 のお客様は、サブスクリプション ライセンスがサポートするセキュリティ機能のみを参照してください。 ポータルの目的は、セキュリティを一元化する方法です。

### <a name="unified-investigations"></a>統一された調査

セキュリティ情報を一元化すると、セキュリティ インシデントを調査する場所が 1 つMicrosoft 365。 主な例は、[**インシデント**] の下の [インシデント **] &の** クイック起動時のアラートMicrosoft 365 Defender。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="[インシデント] ページ (Microsoft 365 Defender" lightbox="../../media/converged-incidents-2.png.png":::

インシデント名を選択すると、セキュリティ情報の集中管理の値を示すページが表示されます。

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="インシデントの概要ページの例Microsoft 365 Defender" lightbox="../../media/converged-incident-info-3.png":::

インシデント ページの上部には、[概要] タブ、[通知] 、[**デバイス**] 、[**ユーザー**] 、[メールボックス] 、[調査] 、[証拠と応答] 、および [Graph]**タブが表示** されます。  詳細については、次のタブを選択します。 たとえば、[ユーザー]タブには、統合ワークロード (Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Cloud Apps) のユーザーの情報と、オンプレミスの Active Directory ドメイン サービス (AD DS)、Azure AD、サードパーティ ID プロバイダーなどのさまざまなソースが表示されます。 詳細については、「ユーザーの調査 [」を参照してください](investigate-users.md)。

環境内のインシデントを確認し、これらのタブをドリルダウンし、さまざまな種類の脅威に対してインシデントに提供された情報にアクセスする方法について理解を深める方法を実践してください。

詳細については、「インシデント」を参照[Microsoft 365 Defender。](incidents-overview.md)

### <a name="improved-processes"></a>改善されたプロセス

共通のコントロールとコンテンツは、同じ場所に表示されるか、データの 1 つのフィードにまとめられて、見つけやすくなります。 たとえば、統一された設定。

#### <a name="unified-settings"></a>統一された設定

:::image type="content" source="../../media/converged-add-role-9.png" alt-text="ポータルの [設定] Microsoft 365 Defender" lightbox="../../media/converged-add-role-9.png":::

#### <a name="permissions--roles"></a>アクセス許可と役割

:::image type="content" source="../../media/converged-roles-5.png" alt-text="グループ&デバイス グループのエンドポイントの役割&を示す [アクセス許可] ページ" lightbox="../../media/converged-roles-5.png":::

グローバル ロールMicrosoft 365 Defenderカスタム ロールを使用してAzure ADアクセスを構成します。 Defender for Endpoint については、「Assign user access to the [Microsoft 365 Defender」を参照してください](/microsoft-365/security/defender-endpoint/assign-portal-access)。 [Defender for Office 365] については、「Microsoft 365 コンプライアンス センター および Microsoft 365 Defender」[を参照してください](../office-365-security/permissions-microsoft-365-compliance-security.md)。

- [Microsoft 365 Defender へのアクセスを管理する](m365d-permissions.md)方法の詳細
- カスタム ロールを作成する[方法の詳細については](custom-roles.md)、Microsoft 365 Defender

> [!NOTE]
> Microsoft Defender for Endpoint in Microsoft 365 Defender は、Microsoft 365 Defender ポータルでアクセスを許可するのと同じ方法で、マネージド セキュリティ サービス プロバイダー [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)へのアクセス許可[をサポートしています](./mssp-access.md)。

#### <a name="integrated-reports"></a>統合レポート

レポートは、レポート内でもMicrosoft 365 Defender。 管理者は、一般的なセキュリティ レポートから始めて、エンドポイント、メール、コラボレーションに関する特定のレポートに分岐できます。 ここでのリンクは、ワークロード構成に基づいて動的に生成されます。

#### <a name="quickly-view-your-microsoft-365-environment"></a>Microsoft 365 環境をすばやく表示する

**ホーム** ページには、セキュリティ チームが必要とする一般的なカードの多くが表示されます。 カードとデータの構成は、ユーザーの役割によって異なります。 ポータルMicrosoft 365 Defender役割ベースのアクセス制御を使用する場合、役割ごとに、毎日のジョブにとってより意味のあるカードが表示されます。

この一目でわかる情報は、組織内の最新の活動についていくのに役立ちます。 Microsoft 365 Defender異なるソースからの信号をまとめ、さまざまなソース環境の全体的なMicrosoft 365します。

カードは次のカテゴリに分類されます。

- **ID** - 組織内の ID を監視し、疑わしいまたは危険な行動を追跡します。 [ID 保護の詳細をご覧ください](/azure/active-directory/identity-protection/overview-identity-protection)。
- **データ** - 無許可のデータ開示につながる可能性のあるユーザー アクティビティを追跡するのに役立ちます。
- **デバイス** - デバイス上のアラート、違反アクティビティ、およびその他の脅威に関する最新情報を取得します。
- **アプリ** - 組織でクラウド アプリがどのように使用されているかについての分析情報を得ます。 [Defender for Cloud Apps で検出されたアプリの詳細を確認します](/cloud-app-security/discovered-apps)。

### <a name="threat-analytics-with-better-data-coverage"></a>より優れたデータ カバレッジを備えた脅威の分析

次の Microsoft 365 Defender 脅威分析統合エクスペリエンスを使用して、新たな脅威を追跡し、対応します。

- Microsoft Defender for Endpoint と Microsoft Defender for Office 365 の間のデータ カバレッジが向上し、インシデント管理、自動調査、修復、およびドメイン全体での予防的または事後対応的な脅威ハンティングの組み合わせが可能になります。
- Microsoft Defender for Endpoint から既に利用可能なエンドポイント データに加えて、Microsoft Defender for Office 365 からのメール関連の検出と軽減。
- Microsoft Defender for Endpoint と Microsoft Defender for Office 365 全体のエンドツーエンドの攻撃ストーリーにアラートを集約して、作業キューを削減し、調査を簡素化および高速化する、脅威関連のインシデントのビュー。
- Microsoft 365 Defender ソリューションによって検出され、ブロックされた攻撃の試み。 さらなる曝露のリスクを軽減し、回復力を高める予防措置を推進するために使用できるデータもあります。
- 実用的な情報にスポットライトを当て、緊急に焦点を合わせ、調査し、レポートから活用するデータをすばやく特定できるようにする拡張された設計。

### <a name="a-centralized-learning-hub"></a>一元化されたラーニング ハブ

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderには</a>、Microsoft セキュリティ ブログ、YouTube の Microsoft セキュリティ コミュニティ、および docs.microsoft.com の公式ドキュメントなどのリソースからの公式ガイダンスを吹き込む学習ハブが含まれています。

学習ハブ内では、Email & Collaboration (Microsoft Defender for Office 365) ガイダンスは、エンドポイント (Microsoft Defender for Endpoint) および Microsoft 365 Defender ラーニング リソースと並べて示されています。

ラーニング ハブは、「Microsoft 365 Defender を使用して調査する方法」 および「Microsoft Defender for Office 365 のベスト プラクティス」などのトピックを中心に編成されたラーニング パスで始まります。 このセクションは現在、Microsoft 内のセキュリティ製品グループによってキュレーションされています。 各ラーニング パスは、概念を理解するのにかかると予想される時間を反映しています。 たとえば、「Microsoft Defender for Office 365 ユーザー アカウントが侵害された場合の手順」は 8 分かかると予想されており、その場で学ぶ価値があります。

コンテンツをクリックした後、このサイトをブックマークして、ブックマークを 'セキュリティ' または 'クリティカル' フォルダーに整理すると便利な場合があります。 すべてのラーニング パスを表示するには、メイン パネルの [すべて表示] リンクをクリックします。

> [!NOTE]
> Microsoft 365 Defender ラーニングハブの上部には、製品 (現在の Microsoft 365 Defender、エンドポイント用 Microsoft Defender、および microsoft Defender for Office 365) を選択できる便利なフィルターがあります。 各セクションの学習リソースの数がリストされていることに注意してください。これは、学習者がトレーニングと学習のために手元にあるリソースの数を追跡するのに役立ちます。
>
> 製品フィルターに沿って、現在のトピック、リソースの種類 (ビデオからウェビナーまで)、セキュリティ領域に関する知識または経験のレベル、セキュリティの役割、および製品の機能が一覧表示されます。

> [!TIP]
> [Microsoft Learn](/learn/)には他にも多くの学習機会があります。 コース[MS-500T02-A: 脅威保護の実装など、認定Microsoft 365があります](/learn/certifications/courses/ms-500t02)。

### <a name="send-us-your-feedback"></a>フィードバックの送信

フィードバックをお寄せください。 常に改善を試みているので、何か見たいものがある場合は、このビデオを見て、フィードバックを読む信頼できる方法を [確認してください](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。

この記事からフィードバックを残すこともできます。 [フィードバックの送信と表示] の下にある最後の [フィードバック] セクションには、オプション *[この製品]* または *[このページ]* があります。

*製品* のフィードバックには、**[この製品]** ボタンを使用してください。

1. 記事の下部にある *[この製品]* を選択します。
    1. これらの指示を読み続ける場合は、ボタンを右クリックして [新しいタブで開く] を選択してください。
2. これにより、**UserVoice フォーラム** に移動します。
3. 2 つのオプションがあります。
    1. テキスト ボックスまで下にスクロール *する コンプライアンス* を改善したり、ユーザーを保護したりするには、次の手順を実行Office 365を貼り *Microsoft 365 Defender。* 結果から自分のようなアイデアを探して賛成票を投じるか、**[新しいアイデアを投稿する]** ボタンを使用できます。
    1. この問題がすでに報告されていると確信し、1 票または複数の票でそのプロファイルを上げたい場合は、UserVoice の右側にある *[フィードバックの送信]* ボックスを使用してください。 [検索] **Microsoft 365 Defender、問題を** 検索し、投票ボタンを使用して状態を上げる。 

記事自体に関するフィードバックは、*[このページ]* を使用してください。 フィードバックしていただき、ありがとうございます。 あなたの声は製品の改善に役立ちます。

### <a name="explore-what-the-microsoft-365-defender-portal-has-to-offer"></a>ポータルが提供するMicrosoft 365 Defenderを確認する

次の機能を引き続き確認Microsoft 365 Defender。

- [インシデントとアラートを管理する](manage-incidents.md)
- [脅威の分析を使用して、新たな脅威を追跡し対応する](threat-analytics.md)
- [アクション センター](m365d-action-center.md)
- [デバイス、メール、アプリ、ID 全体の脅威を探す](./advanced-hunting-query-emails-devices.md)
- [カスタム検出ルール](./custom-detection-rules.md)
- [メールとコラボレーションのアラート](../../compliance/alert-policies.md#default-alert-policies)
- [フィッシング攻撃のシミュレーションを作成し](../office-365-security/attack-simulation-training.md)、[チームをトレーニングするためのペイロードを作成する](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)

## <a name="training-for-security-analysts"></a>セキュリティ アナリスト向けトレーニング

Microsoft Learn のこの学習パスを使用すると、セキュリティMicrosoft 365 Defenderの特定、制御、修復に役立つ情報を理解できます。

|トレーニング: |Microsoft 365 Defender を使用してサイバー攻撃を検出して対応する|
|---|---|
|![Microsoft 365 Defender トレーニング アイコン。](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Microsoft 365 Defender では、エンドポイント、ID、メール、アプリケーション間で脅威信号を統合し、巧妙なサイバー攻撃を包括的に保護することができます。 Microsoft 365 Defender は、インシデントを調査して対応し、継続的な悪意のあるサイバー セキュリティ活動を積極的に検索することができる中心的な環境です。<p> 1 時間 38 分 - ラーニング パス - 5 モジュール|

> [!div class="nextstepaction"]
> [スタート>](/learn/paths/defender-detect-respond/)


## <a name="see-also"></a>関連項目

- [Microsoft 365 Defender の新機能](whats-new.md)
- [Microsoft Defender for Office 365 Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
