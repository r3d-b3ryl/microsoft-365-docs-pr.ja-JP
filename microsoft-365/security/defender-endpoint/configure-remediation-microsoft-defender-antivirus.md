---
title: Microsoft Defender ウイルス対策検出の修復を構成する
description: 脅威をMicrosoft Defender ウイルス対策するときに実行する必要がある操作と、検疫フォルダーに検疫されたファイルを保持する期間を構成する
keywords: 修復、修正、削除、脅威、検疫、スキャン、復元
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 3bb844437bde35e202b177aeba3439f50bf14766
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490131"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Microsoft Defender ウイルス対策検出の修復を構成する


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

スキャンMicrosoft Defender ウイルス対策、検出された脅威を修復または削除します。 特定の脅威Microsoft Defender ウイルス対策対処する方法、修復する前に復元ポイントを作成する必要があるかどうか、および脅威を削除する必要がある場合を構成できます。

この記事では、グループ ポリシーを使用してこれらの設定を構成する方法について説明しますが、グループ ポリシーとグループ ポリシー [Microsoft Endpoint Configuration Manager使用](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings)[Microsoft Intune。](/intune/device-restrictions-configure)

PowerShell コマンドレットまたは WMI クラス[ `Set-MpPreference` を使用して](/powershell/module/defender/set-mppreference)[ `MSFT_MpPreference` これらの](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)設定を構成することもできます。

## <a name="configure-remediation-options"></a>修復オプションの構成

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] を選択します**。

3. ツリーを展開して、Windows **コンポーネントMicrosoft Defender ウイルス対策。** \> 

4. 次の表を使用して場所を選択し、必要に応じてポリシーを編集します。

5. [**OK**] を選択します。

<br/><br/>

|Location|設定|説明|既定の設定 (構成されていない場合)|
|---|---|---|---|
|スキャン|システム復元ポイントの作成|クリーニングまたはスキャンが試行される前に、システムの復元ポイントが毎日作成されます|無効|
|スキャン|スキャン履歴フォルダーからのアイテムの削除を有効にする|スキャン履歴に保持する日数を指定する|30 日間|
|ルート|定期的な修復をオフにする|脅威を自動的に修復Microsoft Defender ウイルス対策するか、エンドポイント ユーザーに何を行うのかを確認するかどうかを指定できます。|無効 (脅威は自動的に修復されます)|
|検疫する|検疫フォルダーからのアイテムの削除を構成する|アイテムを削除する前に検疫に保持する日数を指定する|90 日間|
|Threats|検出時に既定のアクションを実行しない脅威アラート レベルを指定する|ユーザーが検出した脅威Microsoft Defender ウイルス対策レベル (低、中、高、または重大) が割り当てられます。 この設定を使用して、脅威レベルごとにすべての脅威を修復する方法 (検疫、削除、または無視) を定義できます。|該当なし|
|Threats|検出時に既定のアクションを実行しない脅威を指定する|特定の脅威 (脅威 ID を使用) を修復する方法を指定します。 特定の脅威を検疫、削除、または無視するかどうかを指定できます。|該当なし|

> [!IMPORTANT]
> Microsoft Defender ウイルス対策多くの要因に基づいてファイルを検出し、修復します。 修復を完了するには再起動が必要な場合があります。 検出が後で誤検知と判断された場合でも、すべての追加の修復手順が完了した場合は、再起動を完了する必要があります。
>
> 誤検知に基Microsoft Defender ウイルス対策ファイルを検疫する必要がある場合は、デバイスの再起動後に検疫からファイルを復元できます。 「[検疫済みファイルを復元する」を参照Microsoft Defender ウイルス対策。](restore-quarantined-files-microsoft-defender-antivirus.md)
>
> この問題を今後回避するために、スキャンからファイルを除外できます。 詳細については[、「除外の構成と検証」を参照Microsoft Defender ウイルス対策してください](configure-exclusions-microsoft-defender-antivirus.md)。

さらに、修復に[関連する設定については、「](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed)修復に必要なスケジュールされた完全Microsoft Defender ウイルス対策スキャンを構成する」も参照してください。

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策スキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [スケジュールされたスキャンMicrosoft Defender ウイルス対策構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する](run-scan-microsoft-defender-antivirus.md)
- [エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)
- [エンド ユーザー の操作をMicrosoft Defender ウイルス対策する](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
