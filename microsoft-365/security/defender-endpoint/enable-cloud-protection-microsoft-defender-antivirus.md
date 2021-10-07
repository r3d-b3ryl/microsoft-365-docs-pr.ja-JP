---
title: クラウド保護をオンMicrosoft Defender ウイルス対策
description: クラウド保護を有効にし、高速かつ高度な保護機能を利用できます。
keywords: Microsoft Defender ウイルス対策マルウェア対策、セキュリティ、クラウド、一目でブロックする
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 08/31/2021
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 68a98b3ddcc12d185d8b06827ed68044ab062257
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196947"
---
# <a name="turn-on-cloud-protection-in-microsoft-defender-antivirus"></a>クラウド保護をオンMicrosoft Defender ウイルス対策

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender ウイルス対策

[クラウド保護は、Microsoft Defender ウイルス対策、](cloud-protection-microsoft-defender-antivirus.md)リアルタイム、インテリジェントな保護を提供します。 クラウド保護は既定で有効にする必要があります。ただし、組織のニーズに合わせてクラウド保護を構成できます。

## <a name="methods-to-configure-cloud-protection"></a>クラウド保護を構成する方法

次のいずれかの方法Microsoft Defender ウイルス対策使用して、クラウド保護のオンとオフを切り替えます。

- Microsoft エンドポイント マネージャー、構成マネージャー Microsoft Intune含む
- グループ ポリシー
- PowerShell コマンドレット

また、アプリを使用して、個々のエンドポイントでクラウド保護を有効またはWindows セキュリティすることもできます。 

エンドポイントがクラウド保護サービスに接続できるよう、特定のネットワーク接続要件の詳細については、「ネットワーク接続の構成と検証」を [参照してください](configure-network-connections-microsoft-defender-antivirus.md)。

> [!NOTE]
> このWindows 10、このトピックで説明する **Basic** レポート オプションと **Advanced** レポート オプションの違いはありません。 これは従来の違いであり、どちらかの設定を選択すると、クラウド保護の同じレベルになります。 共有される情報の種類や量に違いはありません。 収集する情報の詳細については [、「Microsoft Privacy Statement」を参照してください](https://go.microsoft.com/fwlink/?linkid=521839)。

## <a name="use-intune-to-turn-on-cloud-protection"></a>Intune を使用してクラウド保護を有効にする

1. 管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。

2. [ホーム **] ウィンドウで** 、[デバイス **構成] >選択します**。

3. 構成する **デバイス制限プロファイル** の種類を選択します。 新しいデバイス制限プロファイルの種類を作成 **する** 必要がある場合は、「デバイス制限の設定を構成する」を参照 [Microsoft Intune。](/intune/device-restrictions-configure)

4. [プロパティ **の** \> **構成設定] を選択します。[プロパティ** \> **のMicrosoft Defender ウイルス対策** します。

5. [クラウド配信 **の保護] スイッチで、[** 有効にする] を **選択します**。

6. [サンプル申請 **の前にユーザーに確認する** ] ドロップダウンで、[すべてのデータを **自動的に送信する] を選択します**。

Intune デバイス プロファイルの作成および構成方法など、Intune デバイス プロファイルの詳細については、「デバイス プロファイルのMicrosoft Intune[参照してください。](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-protection"></a>クラウドMicrosoft エンドポイント マネージャーを有効にする

1. 管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。

2. [エンドポイント **セキュリティウイルス** \> **対策] を選択します**。

3. ウイルス対策プロファイルを選択します。 (まだプロファイルを持っていない場合、または新しいプロファイルを作成する場合は、「デバイス制限設定を構成する」を参照[Microsoft Intune。](/intune/device-restrictions-configure)

4. [プロパティ **] を選択します**。 次に、[構成設定] **の横にある**[編集] を **選択します**。

5. [ **クラウド保護]** を展開し、[クラウド配信の保護レベル] ボックス **の一覧** で、次のいずれかを選択します。
   - **高**: 強力なレベルの検出を適用します。
   - **High plus**: High level **を使用し** 、追加の保護手段を適用します (クライアントのパフォーマンスに影響を与える可能性があります)。
   - **ゼロ許容値**: 不明なすべての実行可能ファイルをブロックします。

6. [確認 **] + [保存] の** 順に選択し、[保存] **を選択します**。

マルウェア対策ポリシーの構成Microsoft Endpoint Configuration Manager詳細については、「マルウェア対策ポリシーを作成および展開する方法[: クラウド保護サービス」を参照してください](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)。

## <a name="use-group-policy-to-turn-on-cloud-protection"></a>グループ ポリシーを使用してクラウド保護を有効にする

1. グループ ポリシー管理デバイスで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [管理 **用テンプレート] を選択します**。

4. ツリーを展開して **、MAPS Windowsコンポーネント**  >  **Microsoft Defender ウイルス対策 >します。**

5. [Microsoft **MAPS に参加する] をダブルクリックします**。 オプションがオンになっていることを確認し、[基本マップ] または **[高度なマップ** ] **に設定します**。 **[OK]** を選択します。

6. 詳細な分析が **必要な場合は、[ファイル サンプルの送信] をダブルクリックします**。 最初のオプションが [有効] に設定 **され** 、他のオプションが次のどちらかに設定されている必要があります。

   - **安全なサンプルの送信** (1)
   - **すべてのサンプルを送信** する (3)

   >[!NOTE]
   > [ **安全なサンプルを送信する** (1)] オプションは、ほとんどのサンプルが自動的に送信されるという意味です。 個人情報が含まれている可能性があるファイルは、引き続きプロンプトが表示され、追加の確認が必要です。
   > オプションを Always **Prompt** (0) に設定すると、デバイスの保護状態が低下します。 [送信しない **]** (2) に設定 [](configure-block-at-first-sight-microsoft-defender-antivirus.md)すると、Microsoft Defender for Endpoint の一目でブロック機能が機能しません。

7. **[OK]** を選択します。

## <a name="use-powershell-cmdlets-to-turn-on-cloud-protection"></a>PowerShell コマンドレットを使用してクラウド保護を有効にする

次のコマンドレットは、クラウド保護を有効にできます。

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

PowerShell を Microsoft Defender ウイルス対策と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、PowerShell コマンドレットと Defender コマンドレットを構成およびMicrosoft Defender ウイルス対策実行する」を[参照してください](/powershell/module/defender/)。 [ポリシー CSP - Defender](/windows/client-management/mdm/policy-csp-defender) には、-SubmitSamplesConsent に関する詳細 [な情報があります](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)。

> [!IMPORTANT]
> **-SubmitSamplesConsent** を (既定の推奨設定)、または `SendSafeSamples` `NeverSend` に設定できます `AlwaysPrompt` 。 この `SendSafeSamples` 設定は、ほとんどのサンプルが自動的に送信されるという意味です。 個人情報が含まれている可能性が高いファイルは、続行を求めるプロンプトが表示され、確認が必要になります。
> および `NeverSend` 設定 `AlwaysPrompt` によって、デバイスの保護レベルが下がります。 さらに、 `NeverSend` この設定は、Microsoft Defender for [Endpoint](configure-block-at-first-sight-microsoft-defender-antivirus.md) の一目でブロック機能が機能しないという意味です。

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-protection"></a>クラウドWindowsを有効にする場合は、管理命令 (WMI) を使用します。

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) クラスの Set メソッドを使用します。

```WMI
MAPSReporting
SubmitSamplesConsent
```

許可されるパラメーターの詳細については[、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-protection-on-individual-clients-with-the-windows-security-app"></a>アプリを使用して個々のクライアントでクラウド保護Windows セキュリティする

> [!NOTE]
> [レポート用 **にローカル** 設定の上書きを構成する] 設定が[無効]に設定されている場合、Windows 設定 のクラウドベースの保護設定はグレー表示され、使用できなくなります。 グループ ポリシーを使った変更は、Windows の設定で設定を更新する前に、最初に個別のエンドポイントに展開する必要があります。

1. タスク バー Windows セキュリティ、または Defender のスタート メニューを検索して、アプリを開 **きます**。

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[ウイルス対策] &設定ラベルを **選択** します。

    :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="ウイルス対策と脅威&設定のスクリーンショット":::

3. [クラウドベース **の保護] と [自動** サンプル **送信] が** [オン] に切り替わるか確認 **します**。

   > [!NOTE]
   > グループ ポリシーで自動サンプル送信が構成されている場合、設定は灰色表示され、使用できません。

## <a name="see-also"></a>関連項目

- [Microsoft クラウド保護を使用Microsoft Defender ウイルス対策](cloud-protection-microsoft-defender-antivirus.md)

- [マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

- [PowerShell コマンドレットを使った Microsoft Defender ウイルス対策の管理](use-powershell-cmdlets-microsoft-defender-antivirus.md)
