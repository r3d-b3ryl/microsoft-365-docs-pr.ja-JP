---
title: コンプライアンスマネージャーのための Microsoft コンプライアンス構成アナライザー
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
description: Microsoft コンプライアンス構成アナライザーを使用して Microsoft コンプライアンスマネージャーをすばやく開始して実行する方法について説明します。
ms.openlocfilehash: 1f7d987262a7d390cb9efe2162ae9be9f56c8757
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49072006"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager"></a>コンプライアンスマネージャーのための Microsoft コンプライアンス構成アナライザー

**この記事の内容** Microsoft コンプライアンス構成アナライザーツールをインストールおよび実行して、Microsoft コンプライアンスマネージャーをすばやく開始する方法について説明します。

## <a name="microsoft-compliance-configuration-analyzer-mcca-overview"></a>Microsoft コンプライアンス構成アナライザー (MCCA) の概要

Microsoft コンプライアンス構成アナライザー (MCCA) は、 [Microsoft コンプライアンスマネージャー](compliance-manager.md)を使い始めるときに役立つツールです。 MCCA は、組織の現在の構成を取得し、Microsoft 365 の推奨されるベストプラクティスに照らして検証する PowerShell ベースのユーティリティです。 これらのベストプラクティスは、データ保護とデータガバナンスに関する主要な規制と基準を含む一連のコントロールに基づいています。

MCCA は、コンプライアンスマネージャーのどの改善アクションが現在の Microsoft 365 環境に適用されるかをすばやく確認するのに役立ちます。 MCCA によって識別されるアクションごとに、実装の推奨事項、コンプライアンスマネージャーへの直接リンク、是正措置を開始するための適切なソリューションが提供されます。

MCCA を理解するためのその他のリソースについては、 [GitHub の README の手順](https://github.com/OfficeDev/MCCA#overview)を参照してください。 このページでは、前提条件に関する詳細情報を提供し、完全なインストール手順を示します。 このページにアクセスするには、GitHub アカウントは必要ありません。

## <a name="install-mcca-and-run-a-report"></a>MCCA をインストールしてレポートを実行する

MCCA ツールは、Windows PowerShell を使用してインストールできます。 ツールをダウンロードしてインストールした後は、レポートを実行するためにこれらの手順を繰り返す必要はありません。 MCCA を開くたびに、ログイン資格情報の入力が求められ、更新された新しいレポートが生成されます。

#### <a name="step-1-install-windows-powershell"></a>手順 1: Windows PowerShell をインストールする
開始するには、PowerShell ギャラリーで利用できる Exchange Online PowerShell モジュール (v 2.0.3 以上) が必要です。 [インストール手順を取得](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)します。

#### <a name="step-2-install-mcca"></a>手順 2: MCCA をインストールする

MCCA をインストールするには、管理者モードで PowerShell を使用して開始します。 次の手順を実行します。

1. Windows の [ **スタート** ] ボタンを選択します。
2. 「 **Powershell** 」と入力し、[ **Windows PowerShell** ] を右クリックし、[ **管理者として実行** ] を選択します。
1. コマンドプロンプトで、次のように入力します。

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>手順 3: レポートを実行する

MCCA をインストールした後、MCCA を実行し、レポートを生成できます。 レポートを実行するには、次のようにします。

1. PowerShell を開く
2. 次のコマンドレットを実行します。

    ```powershell
    Get-MCCAReport
    ```
3. MCCA を実行すると、最初のバージョンチェックが行われ、資格情報を求められます。 [ユーザー名の入力を求める] プロンプトで、Microsoft 365 アカウントの電子メールアドレスを使用してサインインします ([レポートを作成するのに適した役割を表示](#role-based-reporting)します)。 パスワードプロンプトで、パスワードを入力します。

レポートの生成には約2-5 分かかります。 完了すると、ブラウザーウィンドウが開き、HTML レポートが表示されます。 ツールを実行するたびに、資格情報の入力が求められ、新しいレポートが生成されます。 このレポートは、ローカルの次のディレクトリに格納されます。

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

このディレクトリから、以前に生成されたレポートにアクセスできます。

## <a name="understanding-your-report"></a>レポートについて

レポートには、生成された日付と時刻に基づいてデータが反映されます。 上部のセクションでは、生成された日時、組織名、およびテナント ID の詳細について説明します。

#### <a name="geolocation-based-reporting"></a>地理位置情報に基づくレポート

[ **メモ** ] セクションは、テナントの地理的な場所に基づいてレポートがカスタマイズされていることを示しています。 このツールには、お住まいの国または地域に固有の推奨事項が記載されています。

地理位置情報の選択を使用して、その地理位置情報に関連する機密情報の種類 (つまり、) を評価し、国または地域に合わせたレポートを生成します。 テナント内のデータに基づいて、geolocations を選択します。

レポートの場所情報を変更するには、地理位置情報 (-Geo) 入力パラメーターを指定する必要があります。 テナントに適用する1つまたは複数の geolocations を選択できます。

特定の場所に基づいてレポートを実行するには、次の手順に従います。

1. PowerShell を開く
2. 特定の地域を指定するには、次の表の番号を使用して、国または地域に対応するコマンドレットを実行します。 複数の数値を入力するには、コンマで区切って指定します。 たとえば、次のコマンドレットでは、Asia-Pacific と日本のカスタマイズされたレポートを実行します。

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  国または地域 | 
  | :------------- | :------------: |
  | 1  | アジア太平洋 |
  | 2  | オーストラリア |
  | 1/3 | カナダ |
  | 4  | ヨーロッパ (フランスを除く)/中東/アフリカ |
  | 5  | フランス |
  | 6  | インド |
  | 7  | 日本 |
  | 8  | 韓国 |
  | 9  | 北米 (カナダを除く) |
  | 10   | 南アメリカ |
  | 11  | 南アフリカ |
  | 12  | スイス |
  | 13  | アラブ首長国連邦 |
  | 14  | 英国 |


 > [!NOTE]
> このレポートには、SWIFT コード、クレジットカード番号などの、MCCA がサポートする国際的な機密情報の種類が常に含まれています。

#### <a name="role-based-reporting"></a>役割に基づくレポート

また、レポートは自分の役割に基づいてカスタマイズされます。

下の表は、どの役割がレポートのどのセクションにアクセスできるかを示しています。 組織内のその他の役割 (以下の表に記載されていません) は、ツールを実行できない可能性があります。また、ツールを実行して、最終レポートの情報へのアクセスに制限を与えることもできます。

![MCCA-役割](../media/compliance-manager-mcca-roles.png "MCCA の役割")

例外:
1. ユーザーは、「Exchange Online で IRM を使用する」セクションとは別に IP のレポートを生成することはできません。
2. ユーザーは、「Exchange Online で IRM を使用する」セクションとは別に IP のレポートを生成できます。
3. ユーザーは、「O365 での通信のコンプライアンスを有効にする」セクションとは別に IP のレポートを生成できます。
4. ユーザーは、「Office の監査を有効にする365」セクションとは別に IP のレポートを生成することはできません。
5. ユーザーは、「Office の監査を有効にする365」セクションとは別に IP のレポートを生成できます。

#### <a name="solutions-summary-section"></a>ソリューションの概要セクション

このレポートの「 **ソリューションの概要** 」セクションには、コンプライアンスマネージャーによってコンプライアンスの状況を改善するために組織が実施できる改善アクションの概要が示されています。

![MCCA-ソリューションの概要](../media/compliance-manager-mcca-solutions.png "MCCA ソリューションの概要画面")

MCCA は、コンプライアンスマネージャーの推奨される改善アクションに対して現在の構成を評価します。 このセクションでは、MCCA ツールによって特定された改善アクションについて説明します。

各 Microsoft ソリューションの横に、コンプライアンスマネージャーの向上アクションに対応する項目の数を示す色分けされたボックスがあります。 アクションは、次の3つの状態状態に分類されます。

- **OK** : この時点で、推奨される条件を満たし、注意を必要としないアクション
- **向上** : 注意が必要な操作
- **推奨事項** : 注意を要することはありませんが、ベストプラクティスをお勧めします。
 
改善と推奨事項を表示するボックスを選択します。

**向上の状態を持つアイテム**

向上アクションの右側にある **改善** ラベルの横にあるドロップダウンを選択します。 現在の設定と推奨される改善アクションについての簡単な概要と詳細が表示されます。 概要には、コンプライアンスマネージャーへの直接リンク、Microsoft 365 コンプライアンスセンターの該当するソリューション、関連ドキュメントが含まれています。

[コンプライアンスマネージャー] リンクをクリックすると、そのソリューション内でまだ実装されていないすべての改善アクションがフィルター処理されたビューに移動します。 そこから、 [コンプライアンススコア](compliance-score-calculation.md)を増やすために達成できるポイント数と、適用される評価、適用される規制、認定資格を確認できます。

DLP では、推奨事項に基づいて事前生成された PowerShell スクリプトを提供する **修復スクリプト** ボタンが用意されています。 PowerShell コンソールに直接コピーして貼り付けることができます。 テストモードで DLP ポリシーを作成します。

**推奨事項の状態のアイテム**

[改善] アクションの右側にある [ **推奨事項** ] ラベルの横にあるドロップダウンを選択します。 改善アクションに関連した、組織の現在の Microsoft 365 環境の概要と、推奨されるベストプラクティスが表示されます。

## <a name="resources"></a>リソース

MCCA のインストール、セットアップ、および使用の詳細については、 [github の README 指示](https://github.com/OfficeDev/MCCA#overview) を参照してください (github アカウントは必要ありません)。

Windows PowerShell の詳細については、「 [PowerShell ドキュメントの使用方法](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)」を開始してください。 「 [Windows PowerShell を起動](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)する」も参照してください。
