---
title: Microsoft 365 セキュリティ センターの概要
description: Microsoft Defender for Office 365 (MDO) と Microsoft Defender for Endpoint (MDE) を、Microsoft Defender for Identity (MDI) と Microsoft Cloud App Security (MCAS) と組み合わせた、Microsoft 365 セキュリティ センターの利点。 この記事では、管理者向けの Microsoft 365 セキュリティ センターの進展について概説します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュリティ センター、モニター、レポート、ID、データ、デバイス、アプリ
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 43e341111ad1cb9b64ac257903d0e79bf24df5bd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903888"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>統合された Microsoft 365 セキュリティ センターの概要

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**適用対象:**

- [Microsoft 365 Defender](./microsoft-threat-protection.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft Defender for Office 365](../office-365-security/office-365-atp.md)

> Microsoft 365 Defender を体験してみませんか? [ラボ環境で評価する](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](./mtp-pilot.md?ocid=cx-evalpilot)こともできます。

改善された **Microsoft 365 セキュリティ センター** ([https://security.microsoft.com](https://security.microsoft.com)) は、保護、検出、調査、および、*メール*、*コラボレーション*、*ID*、*デバイス* の脅威への対応を中央ポータルに統合します。

Microsoft 365 セキュリティ センターは、Microsoft Defender セキュリティ センターや Office 365 セキュリティ/コンプライアンス センターなどの既存の Microsoft セキュリティ ポータルの機能を統合します。 セキュリティ センターは、情報への迅速なアクセス、よりシンプルなレイアウト、およびより簡単に使用できるように関連情報をまとめることを重視しています。 このセンターには次のものが含まれます。

- **[Microsoft Defender for Office 365](../office-365-security/office-365-atp.md)** Microsoft Defender for Office 365 は、メールと Office 365 リソースを保護するための一連の防止、検出、調査、およびハンティング機能を使用して、組織が企業を保護するのに役立ちます。
- **[Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** は、組織内のデバイスに対して、予防的な保護、侵害後の検出、自動調査、および対応を提供します。
- **[Microsoft 365 Defender](microsoft-threat-protection.md)** は、Microsoft の *Extended Detection and Response* (XDR) ソリューションの一部であり、Microsoft 365 セキュリティ ポートフォリオを活用して、ドメイン全体の脅威データを自動的に分析し、単一のダッシュボードで攻撃の全体像を構築します。

Office 365 セキュリティ/コンプライアンス センターまたは Microsoft Defender セキュリティ センターからの変更点に関する情報が必要な場合は、以下を参照してください。

- [Microsoft 365 セキュリティ センターの Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 セキュリティ センターの Defender for Endpoint](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>想定される変化

Office 365 セキュリティ/コンプライアンス センター (protection.office.com) および Microsoft Defender セキュリティ センター (securitycenter.microsoft.com) で使用するすべてのセキュリティ コンテンツは、*Microsoft 365 セキュリティ センター* にあります。

Microsoft 365 セキュリティ センターは、さまざまなワークロードからの信号を単一の統合されたエクスペリエンスに取り込むことにより、セキュリティ チームが調査して攻撃に対応するのを支援します。

- インシデントとアラート
- 検索
- アクション センター
- 脅威の分析

Microsoft 365 セキュリティ センターは、Microsoft Defender for Office 365 および Microsoft Defender for Endpoint を統合する際に、*統一性、明確性、および共通の目標* を強調しています。 統合は、以下にリストされている優先順位に基づいており、各セキュリティ スイートが組み合わせにもたらした機能を犠牲にすることなく行われました。

- 共通の構築ブロック
- 共通の用語
- 共通のエンティティ
- 他のワークロードと同等の機能

## <a name="unified-investigations"></a>統一された調査

セキュリティ センターを合理化すると、Microsoft 365 組織全体のインシデントを調査するための単一のウィンドウが作成されます。 主な例は、Microsoft 365 セキュリティ センターのクイック起動の **[インシデント]** ノードです。

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="MDO の [インシデント] ページ。":::

例として、重大度の **高い** インシデント名をダブルクリックすると、センター統合の利点を示すページが表示されます。

![複数のエンドポイントでの特権エスカレーションを伴う多段階のインシデント。影響を受けるデバイスが 16 個、影響を受けるユーザーが 9 個表示されます。](../../media/converged-incident-info-3.png)

> [!TIP]
> 統合された **[ユーザー]** タブは、問い合わせを開始するのに適した場所です。 この単一ページには、統合されたワークロード (Microsoft Defender for Endpoint、Microsoft Defender for Identity、および MCAS (使用する場合)) のユーザーと、オンプレミスの Active Directory、Azure Active Directory、同期ユーザー、ローカル ユーザー、サードパーティ ユーザーなどのさまざまなソースの情報が表示されます。 [新しい [ユーザー] エクスペリエンス](investigate-users.md)の詳細をご覧ください。

インシデント情報には、影響を受けるメールボックスの横に、ユーザー/ID の詳細とリスクのあるデバイスが表示されます。 また、**調査情報** と収集された **証拠** を関連付けます。 これにより、管理者とセキュリティ運用チームは、リスクの高い 1 つのアラートから、影響を受けるユーザーとメールボックスに簡単にピボットできます。 このページの上部にある **[インシデント]** タブを見ると、この単一の場所から利用できる他の主要なセキュリティ ピボットがあります。

> [!IMPORTANT]
> 特定のインシデントのページの上部に、**[概要]**、**[アラート]**、**[デバイス]**、**[ユーザー]**、**[メールボックス]**、**[調査]**、および **[証拠]** タブが表示されます。

**[調査]** を選択すると、実行中の分析のグラフィックと、修正の状態 (**承認待ち** など) が一覧表示されるページが開きます。 時間をかけて環境内の特定のインシデントを選択し、これらのタブにドリルダウンして、さまざまな種類の脅威のプロファイルを作成する練習をしてください。 精通していると、後の差し迫った調査に役立ちます。

## <a name="improved-processes"></a>改善されたプロセス

共通のコントロールとコンテンツは、同じ場所に表示されるか、データの 1 つのフィードにまとめられて、見つけやすくなります。 たとえば、統一された設定。

### <a name="unified-settings"></a>統一された設定

![[役割] をクリックして、[設定] ページを開きました。このページには、[全般設定]、[アクセス許可]、[API]、および [ルール] が含まれています。 [アクセス許可]、[役割] の順に開きます。 すべての役割を表示する](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>アクセス許可と役割

![エンドポイントの役割とグループ、役割、およびデバイス グループを表示する [アクセス許可と役割] ページ。](../../media/converged-roles-5.png)

 Microsoft 365 セキュリティ センターへのアクセスは、Azure Active Directory グローバル ロールを使用して、またはカスタム ロールを使用して構成されます。 Defender for Endpoint については、「[Microsoft Defender セキュリティ センターへのユーザー アクセスの割り当て](/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access)」をご覧ください。 Defender for Office 365 については、「[Microsoft 365 コンプライアンス センターと Microsoft 365 セキュリティ センターのアクセス許可](../office-365-security/permissions-microsoft-365-compliance-security.md)」をご覧ください。

- [Microsoft 365 Defender へのアクセスを管理する](mtp-permissions.md)方法の詳細
- Microsoft 365 セキュリティ センターで[カスタム ロールを作成する](custom-roles.md)方法の詳細

> [!NOTE]
> Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint は、[Microsoft Defender セキュリティ センターでアクセスが許可される](./mssp-access.md)のと同じ方法で、[マネージド セキュリティ サービス プロバイダー (MSSP) へのアクセスの許可](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access)をサポートします。

### <a name="integrated-reports"></a>統合レポート

レポートは、Microsoft 365 セキュリティ センターでも統合されています。 管理者は、一般的なセキュリティ レポートから始めて、エンドポイント、メール、コラボレーションに関する特定のレポートに分岐できます。 ここでのリンクは、ワークロード構成に基づいて動的に生成されます。

### <a name="quickly-view-your-microsoft-365-environment"></a>Microsoft 365 環境をすばやく表示する

**ホーム** ページには、セキュリティ チームが必要とする一般的なカードの多くが表示されます。 カードとデータの構成は、ユーザーの役割によって異なります。 Microsoft 365 セキュリティ センターは役割ベースのアクセス制御を使用しているため、役割が異なれば、日常業務にとってより意味のあるカードが表示されます。  

この一目でわかる情報は、組織内の最新の活動についていくのに役立ちます。 Microsoft 365 セキュリティ センターは、さまざまなソースからの信号をまとめて、Microsoft 365 環境の全体像を示します。

カードは次のカテゴリに分類されます。

- **ID** - 組織内の ID を監視し、疑わしいまたは危険な行動を追跡します。 [ID 保護の詳細をご覧ください](/azure/active-directory/identity-protection/overview-identity-protection)。
- **データ** - 無許可のデータ開示につながる可能性のあるユーザー アクティビティを追跡するのに役立ちます。
- **デバイス** - デバイス上のアラート、違反アクティビティ、およびその他の脅威に関する最新情報を取得します。
- **アプリ** - 組織でクラウド アプリがどのように使用されているかについての分析情報を得ます。 [Cloud App Security で検出されたアプリの詳細をご覧ください](/cloud-app-security/discovered-apps)。

## <a name="threat-analytics-with-better-data-coverage"></a>より優れたデータ カバレッジを備えた脅威の分析
次の Microsoft 365 Defender 脅威分析統合エクスペリエンスを使用して、新たな脅威を追跡し、対応します。

- Microsoft Defender for Endpoint と Microsoft Defender for Office 365 の間のデータ カバレッジが向上し、インシデント管理、自動調査、修復、およびドメイン全体での予防的または事後対応的な脅威ハンティングの組み合わせが可能になります。 
- Microsoft Defender for Endpoint から既に利用可能なエンドポイント データに加えて、Microsoft Defender for Office 365 からのメール関連の検出と軽減。
- Microsoft Defender for Endpoint と Microsoft Defender for Office 365 全体のエンドツーエンドの攻撃ストーリーにアラートを集約して、作業キューを削減し、調査を簡素化および高速化する、脅威関連のインシデントのビュー。
- Microsoft 365 Defender ソリューションによって検出され、ブロックされた攻撃の試み。 さらなる曝露のリスクを軽減し、回復力を高める予防措置を推進するために使用できるデータもあります。 
- 実用的な情報にスポットライトを当て、緊急に焦点を合わせ、調査し、レポートから活用するデータをすばやく特定できるようにする拡張された設計。

## <a name="a-centralized-learning-hub"></a>一元化されたラーニング ハブ

Microsoft 365 セキュリティ センターには、Microsoft セキュリティ ブログ、YouTube の Microsoft セキュリティ コミュニティ、docs.microsoft.com の公式ドキュメントなどのリソースから公式ガイダンスを作成するラーニング ハブが含まれています。

ラーニング ハブ内では、メールとコラボレーション (Microsoft Defender for Office 365 または MDO) のガイダンスが、Endpoint (Microsoft Defender for Endpoint または MDE) および Microsoft 365 Defender ラーニング リソースと並んでいます。

ラーニング ハブは、「Microsoft 365 Defender を使用して調査する方法」 および「Microsoft Defender for Office 365 のベスト プラクティス」などのトピックを中心に編成されたラーニング パスで始まります。 このセクションは現在、Microsoft 内のセキュリティ製品グループによってキュレーションされています。 各ラーニング パスは、概念を理解するのにかかると予想される時間を反映しています。 たとえば、「Microsoft Defender for Office 365 ユーザー アカウントが侵害された場合の手順」は 8 分かかると予想されており、その場で学ぶ価値があります。

コンテンツをクリックした後、このサイトをブックマークして、ブックマークを 'セキュリティ' または 'クリティカル' フォルダーに整理すると便利な場合があります。 すべてのラーニング パスを表示するには、メイン パネルの [すべて表示] リンクをクリックします。

> [!NOTE]
> Microsoft 365 セキュリティ センターのラーニング ハブの上部には、製品 (現在、Microsoft 365 Defender、Microsoft Defender for Endpoint、および Microsoft Defender for Office 365) から選択できる便利な **フィルター** があります。 各セクションの学習リソースの数がリストされていることに注意してください。これは、学習者がトレーニングと学習のために手元にあるリソースの数を追跡するのに役立ちます。
>
> 製品フィルターに沿って、現在のトピック、リソースの種類 (ビデオからウェビナーまで)、セキュリティ領域に関する知識または経験のレベル、セキュリティの役割、および製品の機能が一覧表示されます。

## <a name="send-us-your-feedback"></a>フィードバックの送信

フィードバックをお寄せください。 私たちは常に改善を目指しています。ご要望がありましたら、[Microsoft 365 Defender のフィードバックを送信してください](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)。

この記事からフィードバックを残すこともできます。 [フィードバックの送信と表示] の下にある最後の [フィードバック] セクションには、オプション *[この製品]* または *[このページ]* があります。

*製品* のフィードバックには、**[この製品]** ボタンを使用してください。

1. 記事の下部にある *[この製品]* を選択します。
    1. これらの指示を読み続ける場合は、ボタンを右クリックして [新しいタブで開く] を選択してください。
2. これにより、**UserVoice フォーラム** に移動します。
3. 2 つのオプションがあります。
    1. テキスト ボックス「*Office 365 でコンプライアンスを改善したり、ユーザーをより適切に保護するにはどうすればよいですか?*」まで下にスクロールして、*Microsoft 365 セキュリティ センター* に貼り付けます。 結果から自分のようなアイデアを探して賛成票を投じるか、**[新しいアイデアを投稿する]** ボタンを使用できます。
    1. この問題がすでに報告されていると確信し、1 票または複数の票でそのプロファイルを上げたい場合は、UserVoice の右側にある *[フィードバックの送信]* ボックスを使用してください。 *Microsoft 365 セキュリティ センター* を検索し、**問題を見つけ、投票ボタンを使用して** そのステータスを上げます。

記事自体に関するフィードバックは、*[このページ]* を使用してください。 フィードバックしていただき、ありがとうございます。 あなたの声は製品の改善に役立ちます。

### <a name="explore-what-the-security-center-has-to-offer"></a>セキュリティ センターが提供するものを調べる

Microsoft 365 セキュリティ センターの特徴と機能を調べてください。

- [インシデントとアラートを管理する](manage-incidents.md)
- [脅威の分析を使用して、新たな脅威を追跡し対応する](threat-analytics.md)
- [アクション センター](./mtp-action-center.md)
- [デバイス、メール、アプリ、ID 全体の脅威を探す](./advanced-hunting-query-emails-devices.md)
- [カスタム検出ルール](./custom-detection-rules.md)
- [メールとコラボレーションのアラート](../../compliance/alert-policies.md#default-alert-policies)
- [フィッシング攻撃のシミュレーションを作成し](../office-365-security/attack-simulation-training.md)、[チームをトレーニングするためのペイロードを作成する](../office-365-security/attack-simulation-training-payloads.md)
 
### <a name="related-information"></a>関連情報
- [Microsoft 365 セキュリティ センター](overview-security-center.md)
- [Microsoft 365 セキュリティ センターの Microsoft Defender for Office 365](microsoft-365-security-center-mdo.md)
- [Microsoft 365 セキュリティ センターの Microsoft Defender for Endpoint](microsoft-365-security-center-mde.md)
- [アカウントを Microsoft Defender for Endpoint から Microsoft 365 セキュリティ センターにリダイレクトする](microsoft-365-security-mde-redirection.md)