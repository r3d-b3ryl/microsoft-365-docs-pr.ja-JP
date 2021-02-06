---
title: コンプライアンス マネージャー向け Microsoft Compliance Configuration Analyzer
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
description: Microsoft コンプライアンス構成アナライザーを使用して、Microsoft コンプライアンス マネージャーを迅速に開始および実行する方法について説明します。
ms.openlocfilehash: 86c4b04deb8313f3013a6d9ad349c0f4112db773
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122397"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>コンプライアンス マネージャー用の Microsoft Compliance Configuration Analyzer (プレビュー)

**この記事では、次の情報を参照してください。** Microsoft Compliance Configure Analyzer ツールをインストールして実行し、Microsoft コンプライアンス 管理をすぐに開始する方法について説明します。

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Microsoft Compliance Configuration Analyzer (MCCA) (プレビュー) の概要

Microsoft Compliance Configuration Analyzer (MCCA) は、Microsoft コンプライアンス マネージャーの使用を開始するのに役立つプレビュー [ツールです](compliance-manager.md)。 MCCA は、組織の現在の構成をフェッチし、Microsoft 365 の推奨ベスト プラクティスに対して検証する PowerShell ベースのユーティリティです。 これらのベスト プラクティスは、データ保護とデータ ガバナンスの主要な規制と基準を含む一連のコントロールに基づいて行います。

MCCA は、コンプライアンス 管理の改善アクションが現在の Microsoft 365 環境に適用されるのを迅速に確認するのに役立ちます。 MCCA によって識別される各アクションには、実装に関する推奨事項が示されます。コンプライアンス マネージャーへの直接リンクと、修正アクションの実行を開始する該当するソリューションへの直接リンクが表示されます。

MCCA を理解する追加のリソースは [、GitHub の README の手順にアクセスする方法です](https://github.com/OfficeDev/MCCA#overview)。 このページでは、前提条件に関する詳細情報を提供し、完全なインストール手順を示します。 このページにアクセスするために GitHub アカウントは必要ない。

**可用性**: MCCA は、Office 365 ライセンスと Microsoft 365 ライセンス、および米国政府機関コミュニティ (GCC) Moderate のお客様のすべての組織で利用できます。GCC High のお客様にサービスを拡張する計画が進行中です。

## <a name="install-mcca-and-run-a-report"></a>MCCA をインストールしてレポートを実行する

MCCA ツールは、次のコマンドを使用してWindows PowerShell。 ツールをダウンロードしてインストールしたら、レポートを実行するためにこれらの手順を繰り返す必要がなされません。 MCCA を開くたび、ログイン資格情報の入力を求め、新しい更新されたレポートが生成されます。

#### <a name="step-1-install-windows-powershell"></a>手順 1: インストールWindows PowerShell
まず、PowerShell ギャラリーで利用できる Exchange Online PowerShell モジュール (v2.0.3 以上) が必要です。 [インストール手順を取得します](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)。

#### <a name="step-2-install-mcca"></a>手順 2: MCCA をインストールする

MCCA をインストールするには、管理者モードで PowerShell を使用して開始します。 次の手順に従います。

1. Windows の [スタート] **ボタンを選択** します。
2. **「PowerShell」と** 入力し、アプリケーションを右クリック **Windows PowerShell、[管理者** として **実行] を選択します**。
1. コマンド プロンプトで、次のコマンドを入力します。

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>手順 3: レポートを実行する

MCCA をインストールした後、MCCA を実行してレポートを生成できます。 レポートを実行するには:

1. PowerShell を開く
2. 次のコマンドレットを実行します。

    ```powershell
    Get-MCCAReport
    ```
3. MCCA を実行すると、初期バージョン チェックが実行され、資格情報が要求されます。 [ユーザー名の入力] プロンプトで、Microsoft 365 アカウントのメール アドレスでサインインします (レポートを作成する対象の役割[を表示します](#role-based-reporting))。 次に、パスワード プロンプトでパスワードを入力します。

レポートの生成に約 2 ~ 5 分かかります。 完了すると、ブラウザー ウィンドウが開き、HTML レポートが表示されます。 ツールを実行すると、資格情報が要求され、新しいレポートが生成されます。 このレポートは、次のディレクトリにローカルに格納されます。

C:\Users \<username> \AppData\Local\Microsoft\MCCA。 

このディレクトリから、以前に生成されたレポートにアクセスできます。

## <a name="understanding-your-report"></a>レポートについて

レポートには、生成日時に基づくデータが反映されます。 上部のセクションでは、生成された時間、組織名、テナント ID に関する詳細が表示されます。

#### <a name="geolocation-based-reporting"></a>地理位置情報ベースのレポート

[ **メモ** ] セクションには、テナントの地理的な場所に基づいてレポートがカスタマイズされたと表示されます。 このツールに記載されている推奨事項は、お客様の国または地域に固有の推奨事項です。

地理位置情報の選択は、その地理位置情報に関連する機密情報の種類 (SIT) を評価し、お客様の国または地域に合ったレポートを生成するために使用されます。 テナント内のデータに基づいて地理位置情報を選択します。

レポートの位置情報を変更するには、地理位置情報 (-Geo) 入力パラメーターを指定する必要があります。 テナントに適用可能な 1 つ以上の地理位置情報を選択できます。

特定の場所に基づいてレポートを実行するには、次の手順に従います。

1. PowerShell を開く
2. 特定の地域を指定するには、国または地域に対応する次の表の番号を使用してコマンドレットを実行します。 複数の数値をコンマで区切って入力します。 たとえば、次のコマンドレットは、ユーザーと日本に対してカスタマイズAsia-Pacific実行します。

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  国または地域 | 
  | :------------- | :------------: |
  | 1  | アジア太平洋 |
  | 2  | オーストラリア |
  | 3  | カナダ |
  | 4  | ヨーロッパ (フランスを除く) / 中東/アフリカ |
  | 5  | フランス |
  | 6  | インド |
  | 7  | 日本 |
  | 8  | 韓国 |
  | 9  | 北米 (カナダを除く) |
  | 10  | 南アメリカ |
  | 11  | 南アフリカ |
  | 12  | スイス |
  | 13  | アラブ首長国連邦 |
  | 14  | 英国 |


 > [!NOTE]
> このレポートには、SWIFT コード、クレジット カード番号など、MCCA でサポートされている国際機密情報の種類が常に含まれます。

#### <a name="role-based-reporting"></a>役割ベースのレポート

また、レポートはロールに基づいてカスタマイズされます。

次の表に、レポートのセクションにアクセスできるロールを示します。 組織内のその他の役割 (以下の表に記載されていない) は、ツールを実行できない場合や、ツールを実行して最終レポートの情報へのアクセスが制限されている場合があります。

![MCCA - 役割](../media/compliance-manager-mcca-roles.png "MCCA の役割")

例外:
1. [Exchange Online で IRM を使用する] セクション以外では、IP のレポートを生成することはできません。
2. ユーザーは、"Exchange Online に IRM を使用する" セクションとは別に IP のレポートを生成できます。
3. ユーザーは、[O365 で通信コンプライアンスを有効にする] セクション以外の IP のレポートを生成できます。
4. ユーザーは、[365 年 365 日に監査を有効にする] セクション以外の IP Office生成できない。
5. ユーザーは、"365 年 365 日に監査を有効にする" セクションOffice IP のレポートを生成できます。

#### <a name="solutions-summary-section"></a>[ソリューションの概要] セクション

レポート **の [ソリューション** の概要] セクションには、コンプライアンス の体制を改善するためにコンプライアンス マネージャーで組織が実行できる改善アクションの概要が示されます。

![MCCA - ソリューションの概要](../media/compliance-manager-mcca-solutions.png "MCCA ソリューションの概要画面")

MCCA は、コンプライアンス マネージャーの推奨される改善アクションに対して現在の構成を評価します。 MCCA ツールによって注意が必要と識別された改善アクションについては、このセクションに記載します。

各 Microsoft ソリューションの横には、コンプライアンス マネージャーの改善アクションに対応するアイテムの数を示す色分けされたボックスがあります。 アクションは、次の 3 つの状態に分かれます。

- **OK**: 推奨される条件を満たすアクションであり、現時点では注意を必要としません
- **改善**: 注意が必要なアクション
- **推奨事項**: 注意が必要ないが、ベスト プラクティスをお勧めするアクション
 
機能強化と推奨事項を表示するボックスを選択します。

**改善ステータスのアイテム**

改善アクションの右側にある **[改善** ] ラベルの横にあるドロップダウンを選択します。 現在の設定と推奨される改善アクションに関する簡単な概要と詳細が表示されます。 概要には、コンプライアンス マネージャー、Microsoft 365 コンプライアンス センターの該当するソリューション、関連ドキュメントへの直接リンクが含まれます。

[コンプライアンス マネージャー] リンクをクリックすると、まだ実装していないソリューション内のすべての改善アクションのフィルタービューが表示されます。 そこから、コンプライアンス スコアを上げ上げするために達成できるポイント数、[](compliance-score-calculation.md)コンプライアンス スコアが適用される評価、適用される規制と認定を確認できます。

DLP には、推奨される機能に基づいて事前に生成された PowerShell スクリプトを提供する修復スクリプト ボタンがあります。 PowerShell コンソールに直接コピーして貼り付けできます。 テスト モードで DLP ポリシーを作成します。

**Recommendation 状態のアイテム**

改善アクションの右側にある **[おすすめ** ] ラベルの横にあるドロップダウンを選択します。 改善アクションに関連する組織の現在の Microsoft 365 環境の概要と、推奨されるベスト プラクティスが表示されます。

## <a name="resources"></a>リソース

MCCA のインストール、セットアップ、使用の詳細については、GitHub の README の手順を参照してください [(GitHub](https://github.com/OfficeDev/MCCA#overview) アカウントは必要ありません)。

PowerShell の詳細についてはWindows PowerShell [PowerShell](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)のドキュメントを参照してください。 「スタートページ[」もWindows PowerShell。](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)
