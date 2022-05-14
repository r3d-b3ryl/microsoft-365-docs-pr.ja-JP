---
title: Microsoft Defender ウイルス対策でクラウド保護を有効にする
description: クラウド保護を有効にして、高速かつ高度な保護機能の恩恵を受けることができます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、クラウド、一目でブロックする
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 02/03/2022
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 38bd804d40c3d5f84e80585f86d906c6a645a668
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65416696"
---
# <a name="turn-on-cloud-protection-in-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策でクラウド保護を有効にする

**適用対象:**

- Microsoft Defender ウイルス対策
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**プラットフォーム**
- Windows

[Microsoft Defender ウイルス対策のクラウド保護](cloud-protection-microsoft-defender-antivirus.md)は、正確でリアルタイムでインテリジェントな保護を提供します。 クラウド保護は既定で有効にする必要があります。ただし、組織のニーズに合わせてクラウド保護を構成できます。

## <a name="methods-to-configure-cloud-protection"></a>クラウド保護を構成する方法

クラウド保護Microsoft Defender ウイルス対策有効または無効にするには、次のいずれかの方法を使用します。

- Microsoft IntuneとConfiguration Managerを含むMicrosoft エンドポイント マネージャー
- グループ ポリシー
- PowerShell コマンドレット

また、Windows セキュリティ アプリを使用して、個々のエンドポイントでクラウド保護をオンまたはオフにすることもできます。 

エンドポイントがクラウド保護サービスに接続できるようにするための特定のネットワーク接続要件の詳細については、「 [ネットワーク接続の構成と検証」を](configure-network-connections-microsoft-defender-antivirus.md)参照してください。

> [!NOTE]
> Windows 10とWindows 11では、この記事で説明する **Basic** レポート オプションと **Advanced** レポート オプションに違いはありません。 これは従来の違いであり、どちらかの設定を選択すると、同じレベルのクラウド保護が行われます。 共有される情報の種類や量に違いはありません。 収集する内容の詳細については、 [Microsoft のプライバシーに](https://go.microsoft.com/fwlink/?linkid=521839)関する声明を参照してください。

## <a name="use-intune-to-turn-on-cloud-protection"></a>Intuneを使用してクラウド保護を有効にする

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。

2. **[ホーム**] ウィンドウで、[**デバイス構成] > [プロファイル**] を選択します。

3. 構成する **デバイス制限プロファイルの** 種類を選択します。 新しい **デバイス制限** プロファイルの種類を作成する必要がある場合は、「[Microsoft Intuneでデバイス制限設定を構成する](/intune/device-restrictions-configure)」を参照してください。

4. **[プロパティ** \> **の構成設定] を選択します。[Microsoft Defender ウイルス対策の編集]** \> を **クリックします**。

5. **クラウド配信保護スイッチで**、[**有効]** を選択します。

6. [ **サンプル送信前にユーザーにプロンプトを表示する** ] ドロップダウンで、[ **すべてのデータを自動的に送信** する] を選択します。

デバイス プロファイルを作成して構成する方法など、Intuneデバイス プロファイルの詳細については、「[Microsoft Intuneデバイス プロファイルとは」](/intune/device-profiles)を参照してください。

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-protection"></a>Microsoft エンドポイント マネージャーを使用してクラウド保護を有効にする

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。

2. **[エンドポイント セキュリティ** \> **ウイルス対策**] を選択します。

3. ウイルス対策プロファイルを選択します。 (まだお持ちでない場合、または新しいプロファイルを作成する場合は、「[Microsoft Intuneでデバイス制限設定を構成する](/intune/device-restrictions-configure)」を参照してください。

4. [**プロパティ**] をクリックします。 **[構成設定]** の横にある **[編集]** を選択します。

5. **[クラウド保護**] を展開し、[**クラウド配信の保護レベル**] ボックスの一覧で、次のいずれかを選択します。
   - **高**: 強力なレベルの検出を適用します。
   - **高いプラス**: **高** レベルを使用し、より多くの保護手段を適用します (クライアントのパフォーマンスに影響を与える可能性があります)。
   - **ゼロ トレランス**: 不明な実行可能ファイルをすべてブロックします。

6. **[確認と保存**] を選択し、[**保存]** を選択します。

Microsoft Endpoint Configuration Managerの構成の詳細については、「[マルウェア対策ポリシーを作成してデプロイする方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)」を参照してください。

## <a name="use-group-policy-to-turn-on-cloud-protection"></a>グループ ポリシーを使用してクラウド保護を有効にする

1. グループ ポリシー管理デバイスで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシー オブジェクトを右クリックし、[**編集]** を選択します。

2. **グループ ポリシー管理エディター** で、[**コンピューターの構成] に** 移動します。

3. [ **管理用テンプレート] を選択します**。

4. ツリーを展開して **コンポーネントをWindowsします** > **Microsoft Defender ウイルス対策 > MAPS**

    > [!NOTE]
    > MAPS の設定は、クラウド配信の保護と同じです。

5. **[Microsoft MAPS に参加** する] をダブルクリックします。 このオプションがオンになっていることを確認し、 **Basic MAPS** または **Advanced MAPS** に設定します。 **[OK]** を選択します。

    検出されたソフトウェアに関する基本的な情報または追加情報を送信することを選択できます。

    - Basic MAPS: Basic メンバーシップは、デバイスで検出されたマルウェアと望ましくない可能性のあるソフトウェアに関する基本情報を Microsoft に送信します。 情報には、ソフトウェアがどこから来たか (URL や部分パスなど)、脅威を解決するために実行されたアクション、およびアクションが成功したかどうかが含まれます。

    - 高度なマップ: 高度なメンバーシップは、基本情報に加えて、マルウェアや望ましくない可能性のあるソフトウェアに関する詳細情報 (ソフトウェアへの完全なパス、ソフトウェアがデバイスに与えた影響に関する詳細情報など) を送信します。

6. **詳細な分析が必要な場合は、[ファイル サンプルの送信**] をダブルクリックします。 最初のオプションが **[有効]** に設定されていること、およびその他のオプションが次のいずれかに設定されていることを確認します。

   - **安全なサンプルを送信する** (1)
   - **すべてのサンプルを送信する** (3)

   >[!NOTE]
   > [ **安全なサンプルの送信** (1)] オプションは、ほとんどのサンプルが自動的に送信されることを意味します。 個人情報が含まれている可能性が高いファイルは引き続き確認を求め、追加の確認が必要になります。
   > **Always Prompt** (0) オプションを設定すると、デバイスの保護状態が低下します。 [**送信しない]** (2) に設定すると、Microsoft Defender for Endpointの [[一目でブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md)] 機能は機能しません。

7. **[OK]** を選択します。

## <a name="use-powershell-cmdlets-to-turn-on-cloud-protection"></a>PowerShell コマンドレットを使用してクラウド保護を有効にする

次のコマンドレットは、クラウド保護を有効にすることができます。

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については、「[PowerShell コマンドレットを使用して、Microsoft Defender ウイルス対策コマンドレットとMicrosoft Defender ウイルス対策コマンドレットを構成して実行](use-powershell-cmdlets-microsoft-defender-antivirus.md)する方法に関[する](/powershell/module/defender/)ページを参照してください。 [ポリシー CSP - Defender には](/windows/client-management/mdm/policy-csp-defender) 、 [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent) に関する詳細情報も含まれています。

> [!IMPORTANT]
> **SubmitSamplesConsent** を `SendSafeSamples` (既定の推奨設定)`NeverSend`、または `AlwaysPrompt`. この設定は `SendSafeSamples` 、ほとんどのサンプルが自動的に送信されることを意味します。 個人情報が含まれている可能性が高いファイルは、続行を求めるメッセージが表示され、確認が必要になります。
> および設定により `NeverSend` 、 `AlwaysPrompt` デバイスの保護レベルが下がります。 さらに、この`NeverSend`設定は、Microsoft Defender for Endpointの [[一目でブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md)] 機能が機能しないことを意味します。

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-protection"></a>Windows管理命令 (WMI) を使用してクラウド保護を有効にする

次のプロパティには、[**MSFT_MpPreference** クラスの **Set** メソッド](/previous-versions/windows/desktop/defender/set-msft-mppreference)を使用します。

```WMI
MAPSReporting
SubmitSamplesConsent
```

許可されるパラメーターの詳細については、「[WINDOWS DEFENDER WMIv2 API」を](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照してください。

## <a name="turn-on-cloud-protection-on-individual-clients-with-the-windows-security-app"></a>Windows セキュリティ アプリを使用して個々のクライアントでクラウド保護を有効にする

> [!NOTE]
> **Microsoft MAPS グループ ポリシーをレポートするためのローカル設定のオーバーライドを構成** する設定が無効に設定 **されている** 場合、Windows 設定の **クラウドベースの保護** 設定はグレー表示され、使用できなくなります。 グループ ポリシーを使った変更は、Windows の設定で設定を更新する前に、最初に個別のエンドポイントに展開する必要があります。

1. Windows セキュリティ アプリを開くには、タスク バーのシールド アイコンを選択するか、スタート メニューで **Windows セキュリティ** を検索します。

2. [ **ウイルス&脅威の保護** ] タイル (または左側のメニュー バーのシールド アイコン) を選択し、[ **管理設定]** で [ **ウイルス&脅威対策の設定**] を選択します。

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="ウイルス&脅威保護の設定" lightbox="../../media/wdav-protection-settings-wdsc.png":::

3. **クラウドベースの保護** と **自動サンプル送信** が **[オン]** に切り替されていることを確認します。

   > [!NOTE]
   > グループ ポリシーを使用して自動サンプル送信が構成されている場合、設定はグレー表示され、使用できなくなります。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策で Microsoft クラウド保護を使用する](cloud-protection-microsoft-defender-antivirus.md)

- [マルウェア対策ポリシーを作成してデプロイする方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

- [PowerShell コマンドレットを使った Microsoft Defender ウイルス対策の管理](use-powershell-cmdlets-microsoft-defender-antivirus.md)
