---
title: 自動調査後の修復アクションを確認する
description: 自動調査の後、修復アクションを確認して承認 (または拒否) します。
keywords: autoir, 自動化, 調査, 検出, 修復, アクション, 保留中, 承認済み
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: how-to
ms.technology: mde
ms.openlocfilehash: 06e2c6c5269b32b29be87f44635d65b9c610c344
ms.sourcegitcommit: e624221597480295b799d56568c4f6f56d40b41d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2022
ms.locfileid: "65535870"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>自動調査後の修復アクションを確認する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/mdb-overview.md)

## <a name="remediation-actions"></a>修復アクション

自動調査が実行されると、 [調査対象](automated-investigations.md) の証拠ごとに判定が生成されます。 判定は、*悪意のある*、*疑わしい*、または *脅威なし* のいずれかです。

に応じて

- 脅威の種類、
- 結果として得られる判定、および
- 組織の [デバイス グループ](/microsoft-365/security/defender-endpoint/machine-groups) の構成方法、

修復アクションは、組織のセキュリティ運用チームが承認した場合にのみ、自動的に実行できます。

いくつかの例を示します。

- **例 1**: Fabrikam のデバイス グループが **[完全] に設定されている - 脅威を自動的に修復** する (推奨設定)。 この場合、自動調査の後に悪意があると見なされるアーティファクトに対して修復アクションが自動的に実行されます ( [完了したアクションの確認](#review-completed-actions)を参照)。

- **例 2**: Contoso のデバイスは、Semi に設定されているデバイス グループに含まれています **。修復には承認が必要** です。 この場合、Contoso のセキュリティ運用チームは、自動調査の後、すべての修復アクションを確認して承認する必要があります ( [保留中のアクションの確認](#review-pending-actions)を参照)。

- **例 3**: Tailspin Toys では、デバイス グループが **[自動応答なし]** に設定されています (推奨されません)。 この場合、自動調査は行われません。 修復アクションは実行されないか保留中であり、デバイスの [アクション センター](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) にはアクションは記録されません (デバイス [グループの管理](/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)に関するページを参照)。

自動的に行われる場合でも承認時でも、自動調査を行うと、1 つ以上の修復アクションが発生する可能性があります。

- ファイルの検疫
- レジストリ キーの削除
- プロセスの強制終了
- サービスの停止
- ドライバーの無効化
- スケジュールされたタスクの実行

## <a name="review-pending-actions"></a>保留中のアクションを確認する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、サインインします。

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。

3. **[保留中]** タブの項目を確認します。

4. ポップアップ ウィンドウを開くアクションを選択します。

5. ポップアップ ウィンドウで情報を確認し、次のいずれかの手順を実行します。

   - [ **調査を開く] ページ** を選択して、調査の詳細を表示します。
   - [ **承認] を** 選択して保留中のアクションを開始します。
   - 保留中のアクションが実行されないようにするには、[ **拒否] を** 選択します。
   - [ **Go hunt** ] を選択して [高度なハンティング](advanced-hunting-overview.md)に移動します。

## <a name="review-completed-actions"></a>完了した処理を確認する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、サインインします。

2. ナビゲーション ウィンドウで、[**アクション センター**] を選択します。

3. [ **履歴** ] タブの項目を確認します。

4. アイテムを選択すると、その修復アクションの詳細が表示されます。

## <a name="undo-completed-actions"></a>完了したアクションを元に戻す

デバイスまたはファイルが脅威でないと判断した場合は、それらのアクションが自動的に実行されたか手動で実行されたかに関係なく、実行された修復アクションを元に戻すことができます。 アクション センターの [ **履歴** ] タブでは、次のいずれかの操作を元に戻すことができます。

|アクション ソース|サポートされているアクション|
|---|---|
|<ul><li>自動調査</li><li>手動応答アクション (以下の注を参照)</li><li>Microsoft Defender ウイルス対策</li></ul>|<ul><li>ドライバーの無効化</li><li>デバイスの分離</li><li>ファイルの検疫</li><li>レジストリ キーの削除</li><li>スケジュールされたタスクの実行</li><li>コードの実行制限</li><li>サービスの停止</li></ul>|

> [!NOTE]
> [Defender for Endpoint Plan 1](defender-endpoint-plan-1.md) と[Microsoft Defender for Business](../defender-business/mdb-overview.md)には、次の手動応答アクションのみが含まれます。
>
> - ウイルス対策スキャンの実行
> - デバイスの分離
> - ファイルを停止して検疫する
> - ファイルをブロックまたは許可するインジケーターを追加する
>
> 詳細については、「Microsoft Defender for Endpoint [プランを比較](defender-endpoint-plan-1-2.md)する」と「[中小企業向けのMicrosoft 365プランのセキュリティ機能の比較](../defender-business/compare-mdb-m365-plans.md)」を参照してください。

### <a name="to-undo-multiple-actions-at-one-time"></a>複数のアクションを一度に元に戻すには

1. アクション センター ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) に移動し、サインインします。

2. **[履歴]** タブで、元に戻す処理を選択します。 必ず、同じアクションの種類を持つ項目を選択してください。 ポップアップ ウィンドウが開きます。

3. ポップアップ ウィンドウで **[元に戻す]** を選択します。

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>複数のデバイス間で検疫からファイルを削除するには

1. アクション センター ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) に移動し、サインインします。

2. [ **履歴** ] タブで、[アクションの種類 **] 検疫ファイル** があるアイテムを選択します。

3. ポップアップ ウィンドウで、[ **このファイルの X インスタンスに適用**] を選択し、[ **元に戻す**] を選択します。

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>自動化レベル、自動調査結果、および結果のアクション

自動化レベルは、特定の修復アクションが自動的に実行されるか、承認時にのみ実行されるかに影響します。 セキュリティ運用チームには、自動調査の結果に応じて、より多くの手順を実行できる場合があります。 次の表は、自動化レベル、自動調査の結果、および各ケースで実行する操作をまとめたものです。

|デバイス グループの設定|自動調査の結果|操作|
|---|---|---|
|**完全 - 脅威を自動的に修復する**<br/>(推奨)|一部の証拠に対して *、悪意のある* ユーザーの判定に達します。 <p> 適切な修復アクションが自動的に実行されます。|[完了した処理を確認する](#review-completed-actions)|
|**完全 - 脅威を自動的に修復する**|証拠の一部については *、疑わしい* という判定に達します。 <p> 修復アクションは、続行するための承認待ちです。|[保留中のアクションを承認 (または拒否) する](#review-pending-actions)|
|**半 - 修復の承認が必要**|一部の証拠に対して *、[悪意]* または *[疑わしい* ] の判定に達します。 <p> 修復アクションは、続行するための承認待ちです。|[保留中のアクションを承認 (または拒否) する](#review-pending-actions)|
|**Semi - コア フォルダー修復の承認が必要**|一部の証拠に対して *、悪意のある* ユーザーの判定に達します。 <p> 成果物がファイルまたは実行可能ファイルであり、オペレーティング システム ディレクトリ (Windows フォルダーや Program files フォルダーなど) にある場合、修復アクションは承認待ちです。 <p> アーティファクトがオペレーティング システム ディレクトリ *にない* 場合は、修復アクションが自動的に実行されます。|<ol><li>[保留中のアクションを承認 (または拒否) する](#review-pending-actions)</li><li>[完了した処理を確認する](#review-completed-actions)</li></ol>|
|**Semi - コア フォルダー修復の承認が必要**|証拠の一部については *、疑わしい* という判定に達します。 <p> 修復アクションは承認待ちです。|[保留中のアクションを承認 (または拒否) します](#review-pending-actions)。|
|**Semi - 一時フォルダー以外の修復の承認が必要**|一部の証拠に対して *、悪意のある* ユーザーの判定に達します。 <p> アーティファクトが、ユーザーのダウンロード フォルダーや一時フォルダーなどの一時フォルダーにないファイルまたは実行可能ファイルの場合、修復アクションは承認待ちです。 <p> アーティファクトが一時フォルダー内にあるファイルまたは実行可能ファイル *の* 場合は、修復アクションが自動的に実行されます。|<ol><li>[保留中のアクションを承認 (または拒否) する](#review-pending-actions)</li><li>[完了した処理を確認する](#review-completed-actions)</li></ol>|
|**Semi - 一時フォルダー以外の修復の承認が必要**|証拠の一部については *、疑わしい* という判定に達します。 <p> 修復アクションは承認待ちです。|[保留中のアクションを承認 (または拒否) する](#review-pending-actions)|
|**すべての** オートメーション レベルまたは **半** オートメーション レベル|証拠の一部に対して、 *脅威が見つかりません* という判定に達します。 <p> 修復アクションは実行されません。また、承認待ちのアクションも実行されません。|[自動調査の詳細と結果を表示する](/microsoft-365/security/defender-endpoint/auto-investigation-action-center)|
|**自動応答なし** (推奨されません)|自動調査は実行されないため、判定に達せず、修復アクションが実行されたり、承認を待ったりすることはありません。|[**フル** オートメーションまたは **半** オートメーションを使用するようにデバイス グループを設定または変更することを検討する](/microsoft-365/security/defender-endpoint/machine-groups)|

すべての判定は [、アクション センター](auto-investigation-action-center.md#the-unified-action-center)で追跡されます。

> [!NOTE]
> [Defender for Business](../defender-business/mdb-overview.md) では、**完全な脅威を自動的に修復** するために、自動調査と修復機能が事前に設定されています。 これらの機能は、既定ですべてのデバイスに適用されます。

## <a name="next-steps"></a>次の手順

- [ライブ応答機能について学習する](live-response.md)
- [高度な捜索を使用して脅威をプロアクティブに検出する](advanced-hunting-overview.md)
- [Microsoft Defender for Endpoint での誤検出/検出漏れに対処する](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>関連項目

- [自動調査の概要](automated-investigations.md)
