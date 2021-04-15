---
title: Microsoft Defender ウイルス対策検出の修復を構成する
description: 脅威を検出した場合の Microsoft Defender ウイルス対策の実行方法と、検疫フォルダーに検疫されたファイルを保持する期間を構成する
keywords: 修復、修正、削除、脅威、検疫、スキャン、復元
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 98bc079bcfd772ada52d699d5f873a187d4ab4c1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765061"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Microsoft Defender ウイルス対策検出の修復を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus がスキャンを実行すると、検出された脅威を修復または削除します。 Microsoft Defender ウイルス対策で特定の脅威に対処する方法、修復する前に復元ポイントを作成する必要があるかどうか、および脅威を削除する必要がある場合を構成できます。

この記事では、グループ ポリシーを使用してこれらの設定を構成する方法について説明しますが [、Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) と Microsoft Intune を [使用することもできます](/intune/device-restrictions-configure)。 

PowerShell コマンドレットまたは WMI クラス[ `Set-MpPreference` を使用して](/powershell/module/defender/set-mppreference)[ `MSFT_MpPreference` これらの](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)設定を構成することもできます。

## <a name="configure-remediation-options"></a>修復オプションの構成

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] を選択します**。

3. ツリーを Windows コンポーネントの Microsoft Defender ウイルス **対策**  >  **に展開します**。 

4. 次の表を使用して場所を選択し、必要に応じてポリシーを編集します。 

5. **[OK]** を選択します。

|場所 | 設定 | 説明 | 既定の設定 (構成されていない場合) |
|:---|:---|:---|:---|
|スキャン | システム復元ポイントの作成 | クリーニングまたはスキャンが試行される前に、システムの復元ポイントが毎日作成されます | 無効|
|スキャン | スキャン履歴フォルダーからのアイテムの削除を有効にする | スキャン履歴に保持する日数を指定する | 30 日間 |
|ルート | 定期的な修復をオフにする | Microsoft Defender Antivirus が脅威を自動的に修復するか、エンドポイント ユーザーに何を行うのかを確認するかどうかを指定できます。 | 無効 (脅威は自動的に修復されます) |
|検疫する | 検疫フォルダーからのアイテムの削除を構成する | アイテムを削除する前に検疫に保持する日数を指定する | 90 日間 |
|Threats | 検出時に既定のアクションを実行しない脅威アラート レベルを指定する | Microsoft Defender ウイルス対策によって検出された脅威には、脅威レベル (低、中、高、または重大) が割り当てられます。 この設定を使用して、脅威レベルごとにすべての脅威を修復する方法 (検疫、削除、または無視) を定義できます。 | 該当なし |
|Threats | 検出時に既定のアクションを実行しない脅威を指定する | 特定の脅威 (脅威 ID を使用) を修復する方法を指定します。 特定の脅威を検疫、削除、または無視するかどうかを指定できます。 | 該当なし |

> [!IMPORTANT]
> Microsoft Defender ウイルス対策は、多くの要因に基づいてファイルを検出し、修復します。 修復を完了するには再起動が必要な場合があります。 検出が後で誤検知と判断された場合でも、すべての追加の修復手順が完了した場合は、再起動を完了する必要があります。
>
> Microsoft Defender ウイルス対策が誤検知に基づいてファイルを検疫した場合は、デバイスの再起動後に検疫からファイルを復元できます。 「Microsoft [Defender ウイルス対策で検疫済みファイルを復元する」を参照してください](restore-quarantined-files-microsoft-defender-antivirus.md)。
> 
> この問題を今後回避するために、スキャンからファイルを除外できます。 「Microsoft [Defender ウイルス対策スキャンの除外の構成と検証」を参照してください](configure-exclusions-microsoft-defender-antivirus.md)。

さらに、修復に [関連する設定については、「修復に必要なスケジュールされた完全な Microsoft Defender ウイルス](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) 対策スキャンを構成する」も参照してください。

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策スキャン オプションの構成](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [スケジュールされた Microsoft Defender ウイルス対策スキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策スキャンの構成と実行](run-scan-microsoft-defender-antivirus.md)
- [エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)
- [エンド ユーザーの Microsoft Defender ウイルス対策の操作を構成する](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策スキャンと修復の結果をカスタマイズ、開始、および確認する](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)