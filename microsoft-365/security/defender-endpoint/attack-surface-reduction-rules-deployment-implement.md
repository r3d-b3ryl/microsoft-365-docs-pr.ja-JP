---
title: 攻撃表面の縮小 (ASR) ルールの展開を実装する
description: 攻撃表面の縮小ルールの展開を実装するためのガイダンスを提供します。
keywords: 攻撃表面の縮小ルールの展開、ASR の展開、asr ルールの有効化、ASR の構成、ホスト侵入防止システム、保護ルール、悪用防止ルール、感染防止ルール、Microsoft Defender for Endpoint、CONFIGURE ASR ルール
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection:
- m365solution-scenario
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: c85dcb985210167e04b51092d66fb59080280581
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64477349"
---
# <a name="step-3-implement-asr-rules"></a>手順 3: ASR ルールを実装する

攻撃表面縮小 (ASR) ルールを実装すると、最初のテスト リングが有効な機能状態に移動します。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-implementation-steps.png" alt-text="ASR ルールを実装する手順" lightbox="images/asr-rules-implementation-steps.png":::
  

## <a name="step-1-transition-asr-rules-from-audit-to-block"></a>手順 1: 監査からブロックへの ASR ルールの移行

1. 監査モードですべての除外が決定された後、トリガーされるイベントが最も少ないルールから始め、一部の ASR ルールを "ブロック" モードに設定します。 「攻撃表面 [の縮小ルールを有効にする」を参照してください](enable-attack-surface-reduction.md)。
2. ポータルのレポート ページを確認Microsoft 365 Defender Microsoft [Defender for Endpoint の「脅威保護レポート」を参照してください](threat-protection-reports.md)。 ASR チャンピオンからのフィードバックも確認します。
3. 必要に応じて除外を絞り込むか、新しい除外を作成します。
4. 問題のあるルールを [監査] に切り替えます。

  >[!Note]
  >問題のあるルール (ノイズが多すぎるルール) の場合は、ルールをオフにするか、監査に戻すよりも除外を作成する方が良いです。 環境に最適な情報を判断する必要があります。

  >[!Tip]
  >使用可能な場合は、ルールの [警告モード] 設定を利用して中断を制限します。 警告モードで ASR ルールを有効にすると、トリガーされたイベントをキャプチャし、エンド ユーザー アクセスを実際にブロックすることなく、中断の可能性を確認できます。 詳細については、「 [ユーザーの警告モード」を参照してください](attack-surface-reduction.md#warn-mode-for-users)。

### <a name="how-does-warn-mode-work"></a>警告モードの動作方法

警告モードは、実質的には Block 命令ですが、ユーザーが特定のフローまたはアプリの後続の実行を "ブロック解除" するオプションを使用します。 デバイス、ユーザー、ファイル、プロセスの組み合わせごとに警告モードのブロックを解除します。 警告モードの情報はローカルに保存され、期間は 24 時間です。

### <a name="step-2-expand-deployment-to-ring-n--1"></a>手順 2: 展開をリング n + 1 に展開する

リング 1 の ASR ルールが正しく構成されていることを確信している場合は、展開の範囲を次のリング (リング n + 1) に拡大できます。

展開プロセスである手順 1 ~ 3 は、以降のリングごとに基本的に同じです。

1. 監査のテスト ルール
2. ASR がトリガーした監査イベントをポータルでMicrosoft 365 Defenderする
3. 除外を作成する
4. レビュー: 必要に応じて除外を絞り込み、追加、または削除する
5. ルールを "ブロック" に設定する
6. ポータルのレポート ページMicrosoft 365 Defenderします。
7. 除外を作成します。
8. 問題のあるルールを無効にするか、監査に戻します。

#### <a name="customize-attack-surface-reduction-rules"></a>攻撃面の減少ルールをカスタマイズする

攻撃表面縮小ルールの展開を引き続き展開する場合、有効にした攻撃表面の縮小ルールをカスタマイズする必要または有益な場合があります。

##### <a name="exclude-files-and-folders"></a>ファイルとフォルダーを除外する

ファイルとフォルダーを攻撃表面の縮小ルールによって評価される対象から除外できます。 除外すると、攻撃表面の縮小ルールでファイルに悪意のある動作が含まれていると検出された場合でも、ファイルの実行がブロックされません。

たとえば、次のランサムウェア ルールを考え出します。

ランサムウェア ルールは、企業のお客様がビジネスの継続性を確保しながら、ランサムウェア攻撃のリスクを軽減するために設計されています。 既定では、ランサムウェア ルールのエラーは注意の側で発生し、まだ十分な評価と信頼を得ていないファイルから保護します。 再フェーズを行う場合、ランサムウェア ルールは、何百万人もの顧客の利用状況指標に基づいて、十分な肯定的な評価と普及率を得てないファイルでのみトリガーされます。 通常、ブロックは自己解決されます。各ファイルの "評価と信頼" の値は、問題ない使用法が増えるほど段階的にアップグレードされます。

ブロックが自己解決されない場合、お客様は自己のリスクで、セルフサービス メカニズムまたは IOC (  IOC) ベースの "許可リスト" 機能を利用して、ファイル自体のブロックを解除できます。

> [!WARNING]
> ファイルまたはフォルダーのブロックを除外または解除すると、安全でないファイルが実行され、デバイスに感染する可能性があります。 ファイルやフォルダーを除外すると、攻撃面の減少ルールで指定された保護機能が著しく低下します。 ルールによってブロックされたファイルの実行が許可され、レポートやイベントは記録されません。

除外は、除外を許可するすべてのルールに適用されます。 リソースの個別のファイル、フォルダー パス、または完全修飾ドメイン名を指定できます。 ただし、除外を特定のルールに制限することはできません。

除外は、除外されたアプリケーションまたはサービスが開始された場合にのみ適用されます。 たとえば、既に実行されている更新サービスの除外を追加すると、サービスが停止して再起動されるまで、更新サービスはイベントをトリガーし続ける。

攻撃表面の縮小は、環境変数とワイルドカードをサポートします。 ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」 [を参照してください](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。
検出すべきではないと思うファイルを検出するルールで問題が発生した場合は、監査モードを使用して [ルールをテストします](evaluate-attack-surface-reduction.md)。

各ルールの [詳細については、攻撃表面の縮小ルール](attack-surface-reduction-rules-reference.md) のリファレンス トピックを参照してください。

##### <a name="use-group-policy-to-exclude-files-and-folders"></a>グループ ポリシーを使用してファイルとフォルダーを除外する

1. グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](https://technet.microsoft.com/library/cc731212.aspx) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] をクリックします**。

3. ツリーを展開して **、WindowsのMicrosoft Defender ウイルス対策** \> **Microsoft Defender Exploit Guard** \>  \> **を表示します**。

4. [攻撃表面の縮小 **ルールからファイル** とパスを除外する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 [ **表示] を** 選択し、[値の名前] 列に各ファイル **またはフォルダーを入力** します。 各 **アイテムの [** 値] **列に** 0 を入力します。

> [!WARNING]
> [値の名前] 列または [値] 列でサポートされていない引用符は **使用** しません。

##### <a name="use-powershell-to-exclude-files-and-folders"></a>PowerShell を使用してファイルとフォルダーを除外する

1. [**powershell]** と入力スタート メニューを **右クリックし**、[管理者Windows PowerShell **実行] を選択します**。

2. 次のコマンドレットを入力します。

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    引き続き使用して `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 、リストにフォルダーを追加します。

    > [!IMPORTANT]
    > リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。 コマンドレットを使用 `Set-MpPreference` すると、既存のリストが上書きされます。

##### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>MDM CSP を使用してファイルとフォルダーを除外する

除外を追加するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 構成サービス プロバイダー (CSP) を使用します。

##### <a name="customize-the-notification"></a>通知をカスタマイズする

ルールがトリガーされた場合の通知をカスタマイズし、アプリまたはファイルをブロックできます。 詳しくは、[Windows セキュリティをご覧](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)ください。

## <a name="additional-topics-in-this-deployment-collection"></a>この展開コレクションのその他のトピック

[ASR ルールの展開の前提条件](attack-surface-reduction-rules-deployment.md)

[手順 1: ASR ルールの展開を計画する](attack-surface-reduction-rules-deployment-plan.md)

[手順 2: ASR ルールをテストする](attack-surface-reduction-rules-deployment-test.md)

[手順 4: ASR ルールを運用化する](attack-surface-reduction-rules-deployment-operationalize.md)
