---
title: クラウドで配信される保護をオン Microsoft Defender ウイルス対策にする
description: クラウドによる保護を有効にし、高速かつ高度な保護機能を利用できます。
keywords: Microsoft Defender ウイルス対策マルウェア対策、セキュリティ、クラウド、一目でブロックする
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: c7a7b3a09a8e8c7cc1a20beab8e2a895702eea27
ms.sourcegitcommit: 132b8dc316bcd4b456de33d6a30e90ca69b0f956
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595340"
---
# <a name="turn-on-cloud-delivered-protection"></a>クラウドによる保護を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> クラウド Microsoft Defender ウイルス対策は、ネットワークとエンドポイントに更新された保護を提供するためのメカニズムです。 クラウド サービスと呼ばれるが、単にクラウドに保存されているファイルの保護ではありません。むしろ、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。

Microsoft Defender ウイルス対策は、複数の検出および防止テクノロジを使用して、正確でリアルタイムでインテリジェントな保護を提供します。 Microsoft Defender for Endpoint 次世代保護の中核となる高度なテクノロジ[を知る](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。

クラウドによる保護Microsoft Defender ウイルス対策オンまたはオフを切り替える方法は、次に示します。

- Microsoft Intune
- Microsoft エンドポイント マネージャー
- グループ ポリシー
- PowerShell コマンドレット。

 また、アプリを使用して個々のクライアントで有効またはWindows セキュリティすることもできます。

クラウド[で配信される保護の](cloud-protection-microsoft-defender-antivirus.md)概要については、「Microsoft クラウドによる保護を使用するMicrosoft Defender ウイルス対策」を参照してください。

エンドポイントがクラウド配信保護サービスに接続できるネットワーク接続要件の詳細については、「ネットワーク接続の構成と検証」を [参照してください](configure-network-connections-microsoft-defender-antivirus.md)。

> [!NOTE]
> このWindows 10、このトピックで説明する **Basic** レポート オプションと **Advanced** レポート オプションの違いはありません。 これは従来の違いであり、どちらかの設定を選択すると、クラウドによる保護の同じレベルになります。 共有される情報の種類や量に違いはありません。 収集する情報の詳細については [、「Microsoft Privacy Statement」を参照してください](https://go.microsoft.com/fwlink/?linkid=521839)。

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Intune を使用してクラウド配信の保護を有効にする

1. 管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。

2. [ホーム **] ウィンドウで** 、[デバイス **構成] >選択します**。

3. 構成する **デバイス制限プロファイル** の種類を選択します。 新しいデバイス制限プロファイルの種類を作成 **する** 必要がある場合は、「デバイス制限の設定を構成する」を参照 [Microsoft Intune。](/intune/device-restrictions-configure)

4. [プロパティ **の** \> **構成設定] を選択します。[プロパティ** \> **のMicrosoft Defender ウイルス対策** します。

5. [クラウド配信 **の保護] スイッチで、[** 有効にする] を **選択します**。

6. [サンプル申請 **の前にユーザーに確認する** ] ドロップダウンで、[すべてのデータを **自動的に送信する] を選択します**。

Intune デバイス プロファイルの作成および構成方法など、Intune デバイス プロファイルの詳細については、「デバイス プロファイルのMicrosoft Intune[参照してください。](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>クラウドMicrosoft エンドポイント マネージャー保護を有効にする方法

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

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>グループ ポリシーを使用してクラウド配信の保護を有効にする

1. グループ ポリシー管理デバイスで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。

3. [管理 **用テンプレート] を選択します**。

4. ツリーを展開して **、MAPS Windowsコンポーネント> Microsoft Defender ウイルス対策 >します。**

5. [Microsoft **MAPS に参加する] をダブルクリックします**。 オプションがオンになっていることを確認し、[基本マップ] または **[高度なマップ** ] **に設定します**。 **[OK]** を選択します。

6. 詳細な分析が **必要な場合は、[ファイル サンプルの送信] をダブルクリックします**。 最初のオプションが [有効] に設定 **され** 、他のオプションが次のどちらかに設定されている必要があります。
    1. **安全なサンプルの送信** (1)
    2. **すべてのサンプルを送信** する (3)

        > [!NOTE]
        > [ **安全なサンプルを送信する** (1)] オプションは、ほとんどのサンプルが自動的に送信されるという意味です。 個人情報が含まれている可能性があるファイルは、引き続きプロンプトが表示され、追加の確認が必要です。
        >
        > オプションを Always **Prompt** (0) に設定すると、デバイスの保護状態が低下します。 [送信しない **]** (2) に設定 [](configure-block-at-first-sight-microsoft-defender-antivirus.md)すると、Microsoft Defender for Endpoint の一目でブロック機能が機能しません。

7. **[OK]** を選択します。

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>PowerShell コマンドレットを使用してクラウド配信の保護を有効にする

次のコマンドレットは、クラウド配信の保護を有効にできます。

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

PowerShell を Microsoft Defender ウイルス対策と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、PowerShell コマンドレットと Defender コマンドレットを構成およびMicrosoft Defender ウイルス対策実行する」を[参照してください](/powershell/module/defender/)。 [ポリシー CSP - Defender](/windows/client-management/mdm/policy-csp-defender) には、-SubmitSamplesConsent に関する詳細 [な情報があります](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)。

> [!NOTE]
> また **、-SubmitSamplesConsent** を `SendSafeSamples` (既定の設定) 、または `NeverSend` に設定できます `AlwaysPrompt` 。 この `SendSafeSamples` 設定は、ほとんどのサンプルが自動的に送信されるという意味です。 個人情報が含まれている可能性があるファイルは、引き続きプロンプトが表示され、追加の確認が必要です。

> [!WARNING]
> **[-SubmitSamplesConsent] を** 設定するか、デバイス `NeverSend` `AlwaysPrompt` の保護レベルを下げる。 さらに、Microsoft Defender for Endpoint の一目でブロック機能が機能しない場合に `NeverSend` 設定します。 [](configure-block-at-first-sight-microsoft-defender-antivirus.md)

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>クラウドWindows保護を有効にする場合は、管理命令 (WMI) を使用します。

次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) クラスの Set メソッドを使用します。

```WMI
MAPSReporting
SubmitSamplesConsent
```

許可されるパラメーターの詳細については[、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>アプリを使用して個々のクライアントでクラウド配信の保護Windows セキュリティする

> [!NOTE]
> [レポート用 **にローカル** 設定の上書きを構成する] 設定が[無効]に設定されている場合、Windows 設定 のクラウドベースの保護設定はグレー表示され、使用できなくなります。 グループ ポリシーを使った変更は、Windows の設定で設定を更新する前に、最初に個別のエンドポイントに展開する必要があります。

1. タスク バー Windows セキュリティ、または Defender のスタート メニューを検索して、アプリを開 **きます**。

2. [ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択し、[ウイルス対策] &設定ラベルを **選択** します。

    :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="ウイルス対策と脅威&設定のスクリーンショット":::

3. [クラウドベース **の保護] と [自動** サンプル **送信] が** [オン] に切り替わるか確認 **します**。

> [!NOTE]
> グループ ポリシーで自動サンプル送信が構成されている場合、設定は灰色表示され、使用できません。

## <a name="related-articles"></a>関連記事

- [クラウド ブロックのタイムアウト期間の構成](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [ブロックを一目で構成する](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [PowerShell コマンドレットを使った Microsoft Defender ウイルス対策の管理](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Pc のセキュリティWindowsセキュリティで保護Endpoint ProtectionをMicrosoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Defender コマンドレット](/powershell/module/defender/)
- [Microsoft クラウドによる保護を使用する方法は、Microsoft Defender ウイルス対策](cloud-protection-microsoft-defender-antivirus.md)
- [マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
