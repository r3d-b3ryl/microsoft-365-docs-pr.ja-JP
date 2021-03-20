---
title: コンプライアンス マネージャー用の Microsoft コンプライアンス構成アナライザー
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンス構成アナライザーを使用して、Microsoft コンプライアンス マネージャーを使用して迅速に立ち上げ、実行する方法について説明します。
ms.openlocfilehash: a77f38dcc0c0215e539c868e47135f5d7194f4b6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906039"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>コンプライアンス マネージャー用 Microsoft コンプライアンス構成アナライザー (プレビュー)

**この記事では、次の情報を参照してください。** Microsoft コンプライアンス構成アナライザー ツールをインストールして実行して、Microsoft コンプライアンス 管理プログラムをすぐに開始する方法について説明します。

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Microsoft コンプライアンス構成アナライザー (MCCA) (プレビュー) の概要

Microsoft コンプライアンス構成アナライザー (MCCA) は [、Microsoft](compliance-manager.md)コンプライアンス マネージャーの開始に役立つプレビュー ツールです。 MCCA は、組織の現在の構成をフェッチし、Microsoft 365 推奨ベスト プラクティスに対して検証する PowerShell ベースのユーティリティです。 これらのベスト プラクティスは、データ保護とデータ ガバナンスの主要な規制と標準を含む一連のコントロールに基づいて行います。

MCCA を使用すると、コンプライアンス 管理の改善アクションが現在の Microsoft 365 環境に適用される状況をすばやく確認できます。 MCCA によって識別される各アクションには、コンプライアンス マネージャーへの直接リンクと、修正アクションの実行を開始する適切なソリューションを含む、実装に関する推奨事項が示されます。

MCCA を理解するもう 1 つのリソースは [、GitHub の README の指示にアクセスする方法です](https://github.com/OfficeDev/MCCA#overview)。 このページでは、前提条件に関する詳細な情報を提供し、完全なインストール手順を示します。 このページにアクセスするには、GitHub アカウントは必要ない。

**可用性**: MCCA は、Office 365 ライセンスと Microsoft 365 ライセンスと米国政府機関コミュニティ (GCC) 中程度および GCC 高い顧客を持つすべての組織で利用できます。DOD のお客様にサービスを拡大する計画が進行中です。

## <a name="install-mcca-and-run-a-report"></a>MCCA をインストールしてレポートを実行する

MCCA ツールは、次のコマンドを使用Windows PowerShell。 ツールをダウンロードしてインストールしたら、レポートを実行するためにこれらの手順を繰り返す必要がなされません。 MCCA を開くごとに、ログイン資格情報を求め、新しい更新されたレポートが生成されます。

#### <a name="step-1-install-windows-powershell"></a>手順 1: インストールWindows PowerShell
まず、PowerShell ギャラリーで使用できる Exchange Online PowerShell モジュール (v2.0.3 以上) が必要です。 [インストール手順を取得します](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)。

#### <a name="step-2-install-mcca"></a>手順 2: MCCA をインストールする

MCCA をインストールするには、まず管理者モードで PowerShell を使用します。 以下の手順に従います。

1. [Windows スタート] **ボタンを選択** します。
2. **「PowerShell」と** 入力し、[**管理者として実行** Windows PowerShellを選択します **。**
1. コマンド プロンプトで、次のコマンドを入力します。

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>手順 3: レポートを実行する

MCCA をインストールした後、MCCA を実行してレポートを生成できます。 レポートを実行するには、次のコマンドを実行します。

1. PowerShell を開く
2. 次のコマンドレットを実行します。

    ```powershell
    Get-MCCAReport
    ```

   GCC High のお客様の場合は、レポートを実行するために追加の入力パラメーターを指定する必要があります。

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. MCCA を実行すると、初期バージョン チェックが実行され、資格情報が要求されます。 [ユーザー名の入力] プロンプトで、Microsoft 365 アカウントの電子メール アドレスでサインインします (レポートの作成に適格な役割[を表示します](#role-based-reporting))。 次に、パスワード プロンプトでパスワードを入力します。

その後、レポートの生成に約 2 ~ 5 分かかります。 完了すると、ブラウザー ウィンドウが開き、HTML レポートが表示されます。 ツールを実行する度に、資格情報を要求し、新しいレポートを生成します。 このレポートは、次のディレクトリにローカルに格納されます。

C:\Users \<username> \AppData\Local\Microsoft\MCCA。 

このディレクトリから、以前に生成されたレポートにアクセスできます。

## <a name="understanding-your-report"></a>レポートについて

レポートには、生成された日時に基づくデータが反映されます。 上部のセクションでは、生成された時間、組織名、テナント ID の詳細を示します。

#### <a name="geolocation-based-reporting"></a>位置情報ベースのレポート

[ **メモ]** セクションでは、テナントの地理的な場所に基づいてレポートがカスタマイズされます。 ツールに記載されている推奨事項は、お客様の国または地域に固有の情報です。

地理位置情報の選択は、その位置情報に関連する機密情報の種類 (SIT) を評価し、国または地域に合ったレポートを生成するために使用されます。 テナント内のデータに基づいて地理位置情報を選択します。

レポートの位置情報を変更するには、位置情報 (-Geo) 入力パラメーターを指定する必要があります。 テナントに適用可能な 1 つ以上の地理的位置を選択できます。

特定の場所に基づいてレポートを実行するには、次の手順に従います。

1. PowerShell を開く
2. 特定の地域を指定するには、国または地域に対応する下の表の番号を使用してコマンドレットを実行します。 複数の数値をコンマで区切って入力します。 たとえば、次のコマンドレットは、ユーザーと日本のユーザー向Asia-Pacific実行します。

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  国または地域 | 
  | :------------- | :------------: |
  | 1 | アジア太平洋 |
  | 2 | オーストラリア |
  | 3 | カナダ |
  | 4  | ヨーロッパ (フランスを除く) / 中東 / アフリカ |
  | 5  | フランス |
  | 6  | インド |
  | 7  | 日本 |
  | 8  | 韓国 |
  | 9  | 北アメリカ (カナダを除く) |
  | 10   | 南アメリカ |
  | 11 | 南アフリカ |
  | 12  | スイス |
  | 13  | アラブ首長国連邦 |
  | 14  | 英国 |


 > [!NOTE]
> このレポートには、SWIFT コード、クレジット カード番号など、MCCA でサポートされる国際的な機密情報の種類が常に含まれます。

#### <a name="role-based-reporting"></a>役割ベースのレポート

また、レポートは役割に基づいてカスタマイズされます。

次の表に、レポートのセクションにアクセスできる役割を示します。 組織内の他の役割 (下の表に記載されていない) は、ツールを実行できないか、ツールを実行し、最終レポートの情報へのアクセスが制限されている可能性があります。

![MCCA - ロール](../media/compliance-manager-mcca-roles.png "MCCA の役割")

例外:
1. [Exchange Online で IRM を使用する] セクション以外では、IP のレポートを生成することはできません。
2. ユーザーは、[Exchange Online で IRM を使用する] セクション以外の IP のレポートを生成できます。
3. ユーザーは、[O365 で通信コンプライアンスを有効にする] セクションとは別に、IP のレポートを生成できます。
4. ユーザーは、[365 で監査を有効にする] セクション以外の IP Office生成できない。
5. ユーザーは、[365 で監査を有効にする] セクションとは別に、IP Office生成できます。

#### <a name="solutions-summary-section"></a>[ソリューションの概要] セクション

レポート **の [ソリューションの** 概要] セクションには、コンプライアンス 体制の向上に役立つコンプライアンス マネージャーで組織が実行できる改善アクションの概要が示されています。

![MCCA - ソリューションの概要](../media/compliance-manager-mcca-solutions.png "MCCA ソリューションの概要画面")

MCCA は、コンプライアンス マネージャーで推奨される改善アクションに対して現在の構成を評価します。 MCCA ツールで注意が必要と識別される改善アクションは、このセクションに一覧表示されます。

各 Microsoft ソリューションの横には、コンプライアンス マネージャーの改善アクションに対応するアイテムの数を示す色分けされたボックスがあります。 アクションは、次の 3 つの状態に分割されます。

- **OK**: 推奨される条件を満たすアクションで、現時点では注意が必要ない
- **改善**: 注意が必要なアクション
- **推奨事項**: 注意を必要としませんが、ベスト プラクティスを推奨するアクション
 
ボックスを選択して、改善点と推奨事項を表示します。

**[改善] 状態のアイテム**

改善アクションの右側にある **[改善** ] ラベルの横にあるドロップダウンを選択します。 現在の設定と推奨される改善アクションに関する簡単な概要と詳細が表示されます。 概要には、コンプライアンス マネージャーへの直接リンク、Microsoft 365 コンプライアンス センターの該当するソリューション、および関連するドキュメントが含まれます。

[コンプライアンス マネージャー] リンクをクリックすると、まだ実装していないソリューション内のすべての改善アクションのフィルタービューが表示されます。 そこから、コンプライアンス スコアを上げ、適用する評価、適用される規制[](compliance-score-calculation.md)と認定を増やして得るポイントの数を確認できます。

DLP の場合、推奨される情報に基づいて事前に生成された PowerShell スクリプトを提供する [修復スクリプト] ボタンがあります。 PowerShell コンソールにコピーして直接貼り付けます。 テスト モードで DLP ポリシーを作成します

**推奨事項の状態を持つアイテム**

改善アクションの右側にある **[おすすめ** ] ラベルの横にあるドロップダウンを選択します。 組織の現在の Microsoft 365 環境の概要と、推奨されるベスト プラクティスが表示されます。

## <a name="resources"></a>リソース

MCCA のインストール、セットアップ、および使用の詳細については、GitHub の README の手順 [(GitHub](https://github.com/OfficeDev/MCCA#overview) アカウントは必要ありません) を参照してください。

詳細については、「PowerShell Windows PowerShell [の使い方」を参照してください](/powershell/scripting/how-to-use-docs?view=powershell-7)。 [「Starting Windows PowerShell」も参照してください](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)。