---
title: Microsoft Purview 用の構成アナライザー
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Configuration Analyzer for Microsoft Purview を使用して、Microsoft Purview コンプライアンス マネージャーを使用してすばやく起動して実行する方法について説明します。
ms.openlocfilehash: d2e5fbc0d928fb5931139a274cf9cce5bdc4d983
ms.sourcegitcommit: 85799f0efc06037c1ff309fe8e609bbd491f9b68
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66573949"
---
# <a name="configuration-analyzer-for-microsoft-purview-camp"></a>Configuration Analyzer for Microsoft Purview (CAMP)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

**この記事では、次の操作を行います。** Configuration Analyzer for Microsoft Purview (CAMP) ツールをインストールして実行し、Microsoft Purview Compliance Manger の概要を確認する方法について説明します。

## <a name="compliance-configuration-analyzer-camp-overview"></a>コンプライアンス構成アナライザー (CAMP) の概要

Configuration Analyzer for Microsoft Purview (CAMP) は、 [Microsoft Purview コンプライアンス マネージャー](compliance-manager.md)の使用を開始するのに役立つツールです。 CAMP は、組織の現在の構成をフェッチし、Microsoft 365 推奨のベスト プラクティスに照らして検証する PowerShell ベースのユーティリティです。 これらのベスト プラクティスは、データ保護とデータ ガバナンスに関する主要な規制と標準を含む一連の制御に基づいています。

CAMP を使用すると、コンプライアンス マネージャーのどの改善アクションが現在の Microsoft 365 環境に適用されているかをすばやく確認できます。 CAMP によって識別される各アクションには、コンプライアンス マネージャーへの直接リンクと、修正アクションの実行を開始するための該当するソリューションを含む、実装に関する推奨事項が表示されます。

前提条件と完全なインストール手順など、CAMP の詳細については、 [GitHub の README の手順を参照してください](https://github.com/OfficeDev/CAMP#overview)。 このページにアクセスするために GitHub アカウントは必要ありません。

#### <a name="availability"></a>Availability
CAMP は、Office 365および Microsoft 365 ライセンスと米国政府機関コミュニティ (GCC) Moderate、GCC High、および国防総省 (DoD) のお客様のすべての組織が利用できます。

#### <a name="roles"></a>役割

CAMP にアクセスして使用したり、レポート内の情報にアクセスしたりするには、特定のユーザー ロールが必要です。 [GitHub の CAMP 前提条件に関する情報を参照してください](https://github.com/OfficeDev/CAMP#pre-requisites)。

## <a name="install-camp-and-run-a-report"></a>CAMP をインストールしてレポートを実行する

WINDOWS POWERSHELLを使用して CAMP ツールをインストールできます。 ツールをダウンロードしてインストールしたら、レポートを実行するためにこれらの手順を繰り返す必要はありません。 CAMP を開くたびに、ログインするように求められ、更新された新しいレポートが生成されます。

### <a name="step-1-install-the-exchange-online-powershell-v2-module"></a>手順 1: Exchange Online PowerShell V2 モジュールをインストールする

まず、PowerShell ギャラリーで使用できる Exchange Online PowerShell モジュール (v2.0.3 以降) が必要です。 インストール手順については、「 [EXO V2 モジュールのインストールと保守](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)」を参照してください。

### <a name="step-2-install-camp"></a>手順 2: CAMP をインストールする

CAMP をインストールするには、まず PowerShell を管理者モードで使用します。 次の手順に従います。

1. [Windows **スタート]** ボタンを選択します。
1. **PowerShell** と入力し、**Windows PowerShell** を右クリックし、[**管理者として実行**] を選択します。
1. コマンド プロンプトに次のコマンドを入力します。

    ```powershell
    Install-Module -Name CAMP
    ```

### <a name="step-3-run-a-report"></a>手順 3: レポートを実行する

CAMP をインストールした後、CAMP を実行してレポートを生成できます。 レポートを実行するには:

1. PowerShell を開く
2. 次のコマンドレットを実行します。

    ```powershell
    Get-CAMPReport
    ```

    GCC High のお客様の場合は、レポートを実行するために追加の入力パラメーターを指定する必要があります。

    ```powershell
    Get-CAMPReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. CAMP が実行されると、初期バージョンチェックが実行され、資格情報が要求されます。 [ユーザー名の入力] プロンプトで、Microsoft 365 アカウントのメール アドレスでサインインします ([レポートの作成に適したロールを表示します](https://github.com/OfficeDev/CAMP#pre-requisites))。 次に、パスワード プロンプトでパスワードを入力します。

レポートの生成には約 2 ~ 5 分かかります。 完了すると、ブラウザー ウィンドウが開き、HTML レポートが表示されます。 ツールを実行するたびに、資格情報が要求され、新しいレポートが生成されます。 このレポートは、ディレクトリ C: \ Users \ *username* \ AppData \ Local \ Microsoft \ CAMP にローカルに格納されます。

このディレクトリから以前に生成されたレポートにアクセスできます。

## <a name="understanding-your-report"></a>レポートについて

レポートには、レポートが生成された日時に基づいてデータが反映されます。 上部のセクションでは、生成された日時、組織名、テナント ID について詳しく説明します。

### <a name="geolocation-based-reporting"></a>位置情報ベースのレポート

**[メモ]** セクションでは、テナントの地理的な場所に基づいてレポートがカスタマイズされていることを示します。 ツールに一覧表示される推奨事項は、お使いの国または地域に固有です。

位置情報の選択は、その位置情報に関連する機密情報の種類 (SIT) を評価し、お客様の国または地域に合ったレポートを生成するために使用されます。 テナント内のデータに基づいて位置情報を選択します。

レポートの位置情報を変更するには、地理位置情報 (-Geo) 入力パラメーターを指定する必要があります。 テナントに適用できる 1 つまたは複数の位置情報を選択できます。

特定の場所に基づいてレポートを実行するには、次の手順に従います。

1. PowerShell を開く
2. 特定のリージョンを指定するには、国または地域に対応する次の表の番号を使用してコマンドレットを実行します。 コンマで区切って複数の数値を入力します。 たとえば、次のコマンドレットは、Asia-Pacificと日本のカスタマイズされたレポートを実行します。

    ```powershell
    Get-CAMPReport -Geo @(1,7)
    ```

  | Input |  国または地域 |
  | :------------- | :------------: |
  | 1 | アジア太平洋 |
  | 2 | オーストラリア |
  | 3 | カナダ |
  | 4 | ヨーロッパ (フランスを除く) / 中東 / アフリカ |
  | 5 | フランス |
  | 6  | インド |
  | 7  | 日本 |
  | 8  | 韓国 |
  | 9  | 北米 (カナダを除く) |
  | 10 | 南アメリカ |
  | 11 | 南アフリカ |
  | 12  | スイス |
  | 13 | アラブ首長国連邦 |
  | 14 | 英国 |

  > [!NOTE]
  > レポートには、SWIFT コード、クレジット カード番号などの CAMP でサポートされている国際機密情報の種類が常に含まれます。

### <a name="role-based-reporting"></a>ロールベースのレポート

また、レポートはロールに基づいてカスタマイズされます。 [GitHub の CAMP 前提条件情報](https://github.com/OfficeDev/CAMP#pre-requisites)では、レポートのどのセクションにアクセスできるロールが示されています。 組織内の他のロールがツールを実行できない場合や、ツールを実行し、最終レポートの情報へのアクセスが制限されている場合があります。

### <a name="solutions-summary-section"></a>[ソリューションの概要] セクション

レポートの **[ソリューションの概要** ] セクションには、コンプライアンス体制を改善するために組織がコンプライアンス マネージャーで実行できる改善アクションの概要が示されています。

![MCCA - ソリューションの概要。](../media/compliance-manager-mcca-solutions.png "CAMP ソリューションの概要画面")

CAMP は、コンプライアンス マネージャーで推奨される改善アクションに対して現在の構成を評価します。 このセクションでは、CAMP ツールによって注意が必要であると識別されたすべての改善アクションを一覧表示します。

各 Microsoft ソリューションの横には、コンプライアンス マネージャーの改善アクションに対応する項目の数を示す色分けされたボックスがあります。 アクションは、次の 3 つの状態に分割されます。

- **OK**: 推奨される条件を満たし、現時点で注意を必要としないアクション
- **改善**: 注意が必要なアクション
- **推奨事項**: 注意は必要ないが、ベスト プラクティスをお勧めするアクション

改善点と推奨事項を表示するボックスを選択します。

#### <a name="items-with-the-improvement-status"></a>改善状態のアイテム

改善アクションの右側にある **[改善** ] ラベルの横にあるドロップダウンを選択します。 現在の設定と推奨される改善アクションに関する簡単な概要と詳細が表示されます。 概要には、コンプライアンス マネージャーへの直接リンク、Microsoft Purview コンプライアンス ポータルの該当するソリューション、および関連ドキュメントが含まれます。

コンプライアンス マネージャーのリンクを選択すると、まだ実装していないソリューション内のすべての改善アクションのフィルター処理されたビューが表示されます。 そこから、 [コンプライアンス スコア](compliance-score-calculation.md)を向上させるために達成できるポイントの数と、それらが適用される評価、および適用される規制と認定を確認できます。

DLP の場合、推奨される内容に基づいて事前に生成された PowerShell スクリプトを提供する **[修復** スクリプト] ボタンがあります。 コピーして PowerShell コンソールに直接貼り付けることができます。 テスト モードで DLP ポリシーが作成されます

#### <a name="items-with-recommendation-status"></a>推奨事項の状態を持つアイテム

改善アクションの右側にある **[推奨事項** ] ラベルの横にあるドロップダウンを選択します。 改善アクションに関連する組織の現在の Microsoft 365 環境の概要と、推奨されるベスト プラクティスが表示されます。

## <a name="resources"></a>リソース

CAMP のインストール、セットアップ、および使用の詳細については、 [GitHub の README の手順](https://github.com/OfficeDev/CAMP#overview) を参照してください (GitHub アカウントは必要ありません)。

Windows PowerShellの詳細については、[PowerShell のドキュメントの使用方法](/powershell/scripting/how-to-use-docs)を参照してください。 [Windows PowerShellの開始](/powershell/scripting/windows-powershell/starting-windows-powershell)も参照してください。
