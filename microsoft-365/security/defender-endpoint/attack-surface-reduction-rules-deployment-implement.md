---
title: 攻撃面の減少 (ASR) ルールを有効にする
description: 攻撃表面縮小ルールの展開を実装するためのガイダンスを提供します。
keywords: 攻撃表面の縮小ルールの展開、ASR 展開、ASR の有効化、ASR の構成、ホスト侵入防止システム、保護規則、悪用防止ルール、悪用防止ルール、悪用防止ルール、感染防止ルール、Microsoft Defender for Endpoint、ASR 規則の構成
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
- M365-security-compliance
- m365solution-asr-rules
- highpri
ms.date: 1/18/2022
ms.openlocfilehash: 3a7b59513681881ad37aa816f55920438925c13e
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67478467"
---
# <a name="enable-attack-surface-reduction-asr-rules"></a>攻撃面の減少 (ASR) ルールを有効にする

攻撃表面縮小 (ASR) ルールを実装すると、最初のテスト リングが有効な機能状態に移行されます。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-implementation-steps.png" alt-text="ASR 規則を実装する手順" lightbox="images/asr-rules-implementation-steps.png":::
  

## <a name="step-1-transition-asr-rules-from-audit-to-block"></a>手順 1: ASR ルールを監査からブロックに移行する

1. 監査モード中にすべての除外が決定されたら、トリガーされたイベントが最も少ないルールから始めて、一部の ASR ルールを "ブロック" モードに設定し始めます。 「 [攻撃対象の縮小ルールを有効にする」を参照してください](enable-attack-surface-reduction.md)。
2. Microsoft 365 Defender ポータルでレポート ページを確認します。[Microsoft Defender for Endpointの脅威保護レポートを](threat-protection-reports.md)参照してください。 ASR チャンピオンからのフィードバックも確認してください。
3. 除外を絞り込むか、必要に応じて新しい除外を作成します。
4. 問題のあるルールを監査に戻します。

  >[!Note]
  >問題のあるルール (ノイズが多すぎるルール) の場合は、ルールをオフにしたり、監査に切り替えたりするよりも、除外を作成することをお勧めします。 環境に最適なものを決定する必要があります。

  >[!Tip]
  >使用可能な場合は、ルールの [警告モード] 設定を利用して中断を制限します。 警告モードで ASR ルールを有効にすると、実際にエンド ユーザーアクセスをブロックすることなく、トリガーされたイベントをキャプチャし、潜在的な中断を表示できます。 詳細情報: [ユーザーの警告モード](attack-surface-reduction.md#warn-mode-for-users)。

### <a name="how-does-warn-mode-work"></a>警告モードのしくみ

警告モードは事実上ブロック命令ですが、ユーザーが特定のフローまたはアプリの後続の実行を "ブロック解除" するオプションを使用します。 警告モードは、デバイス、ユーザー、ファイル、プロセスの組み合わせごとにブロックを解除します。 警告モードの情報はローカルに格納され、期間は 24 時間です。

### <a name="step-2-expand-deployment-to-ring-n--1"></a>手順 2: 展開を展開して n + 1 を呼び出す

リング 1 の ASR 規則が正しく構成されていることを確信している場合は、展開の範囲を次のリング (リング n + 1) に広げます。

デプロイ プロセス (手順 1 ~ 3) は、後続のリングごとに本質的に同じです。

1. 監査のテスト 規則
2. Microsoft 365 Defender ポータルで ASR によってトリガーされた監査イベントを確認する
3. 除外を作成する
4. レビュー: 必要に応じて除外を絞り込み、追加、または削除する
5. ルールを "ブロック" に設定する
6. Microsoft 365 Defender ポータルでレポート ページを確認します。
7. 除外を作成します。
8. 問題のあるルールを無効にするか、監査に切り替えます。

#### <a name="customize-attack-surface-reduction-rules"></a>攻撃面の減少ルールをカスタマイズする

攻撃面縮小ルールの展開を拡大し続けるにつれて、有効にした攻撃面の縮小ルールをカスタマイズすることが必要または有益な場合があります。

##### <a name="exclude-files-and-folders"></a>ファイルとフォルダーを除外する

ファイルとフォルダーを、攻撃面の縮小規則によって評価されないように選択できます。 除外した場合、攻撃対象の縮小ルールでファイルに悪意のある動作が含まれていることが検出された場合でも、ファイルの実行はブロックされません。

たとえば、ランサムウェアルールについて考えてみましょう。

ランサムウェアルールは、企業のお客様がランサムウェア攻撃のリスクを軽減し、ビジネス継続性を確保できるように設計されています。 既定では、ランサムウェアルールは注意の側でエラーが発生し、十分な評判と信頼をまだ達成していないファイルから保護します。 再エンファサイズを行うために、ランサムウェア ルールは、何百万人もの顧客の使用状況メトリックに基づいて、十分な肯定的な評判と普及率を得ていないファイルに対してのみトリガーされます。 通常、各ファイルの "評判と信頼" の値は問題のない使用量が増えるにつれて段階的にアップグレードされるため、ブロックは自己解決されます。

ブロックが適時に自己解決されない場合、お客様は _自己責任で_ 、セルフサービス メカニズムまたは侵害のインジケーター (IOC) ベースの "許可リスト" 機能を使用して、ファイル自体のブロックを解除できます。

> [!WARNING]
> ファイルまたはフォルダーを除外またはブロック解除すると、安全でないファイルが実行され、デバイスに感染する可能性があります。 ファイルやフォルダーを除外すると、攻撃面の減少ルールで指定された保護機能が著しく低下します。 ルールによってブロックされたファイルの実行は許可され、レポートやイベントは記録されません。

除外は、除外を許可するすべてのルールに適用されます。 リソースの個々のファイル、フォルダー パス、または完全修飾ドメイン名を指定できます。 ただし、除外を特定のルールに制限することはできません。

除外は、除外されたアプリケーションまたはサービスが開始されたときにのみ適用されます。 たとえば、既に実行されている更新サービスの除外を追加した場合、サービスが停止して再起動されるまで、更新サービスは引き続きイベントをトリガーします。

攻撃面の縮小では、環境変数とワイルドカードがサポートされます。 ワイルドカードの使用については、 [ファイル名とフォルダーパスまたは拡張子の除外リストでワイルドカードを使用](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)する方法に関するページを参照してください。
検出すべきでないと思われるファイルを検出するルールで問題が発生した場合は、 [監査モードを使用してルールをテストします](evaluate-attack-surface-reduction.md)。

各ルールの詳細については、 [攻撃面の縮小ルールのリファレンス](attack-surface-reduction-rules-reference.md) トピックを参照してください。

##### <a name="use-group-policy-to-exclude-files-and-folders"></a>グループ ポリシーを使用してファイルとフォルダーを除外する

1. グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](https://technet.microsoft.com/library/cc731212.aspx) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **グループ ポリシー管理エディター** で、[**コンピューターの構成**] に移動し、[**管理用テンプレート**] をクリックします。

3. ツリーを **Windows コンポーネント** \> **に展開します。Microsoft Defender ウイルス対策** \> **Microsoft Defender Exploit Guard** \> **攻撃の表面の縮小**。

4. [ **攻撃対象の縮小ルールからファイルとパスを除外する] 設定を** ダブルクリックし、オプションを **[有効]** に設定します。 [ **表示]** を選択し、[ **値名** ] 列に各ファイルまたはフォルダーを入力します。 各項目の **[値**] 列に **「0**」と入力します。

> [!WARNING]
> **[値名]** 列または [**値**] 列ではサポートされていないため、引用符は使用しないでください。

##### <a name="use-powershell-to-exclude-files-and-folders"></a>PowerShell を使用してファイルとフォルダーを除外する

1. スタート メニューに「**powershell**」と入力し、**[Windows PowerShell]** を右クリックして **[管理者として実行]** を選択します。

2. 次のコマンドレットを入力します。

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    引き続き使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` して、リストにフォルダーを追加します。

    > [!IMPORTANT]
    > リストにアプリを追加または追加するために使用 `Add-MpPreference` します。 コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。

##### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>MDM CSP を使用してファイルとフォルダーを除外する

除外を追加するには、 [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 構成サービス プロバイダー (CSP) を使用します。

##### <a name="customize-the-notification"></a>通知のカスタマイズ

ルールがトリガーされ、アプリまたはファイルがブロックされたときの通知をカスタマイズできます。 [Windows セキュリティ](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)の記事を参照してください。

## <a name="additional-topics-in-this-deployment-collection"></a>このデプロイ コレクションのその他のトピック

[攻撃面の縮小 (ASR) ルールの展開の概要](attack-surface-reduction-rules-deployment.md)

[攻撃面の縮小 (ASR) ルールの展開を計画する](attack-surface-reduction-rules-deployment-plan.md)

[攻撃面の減少 (ASR) ルールをテストする](attack-surface-reduction-rules-deployment-test.md)

[攻撃面の減少 (ASR) ルールの運用化](attack-surface-reduction-rules-deployment-operationalize.md)

[攻撃面の減少 (ASR) ルールの参照](attack-surface-reduction-rules-reference.md)
