---
title: Microsoft Defender ウイルス対策でクラウドで提供される保護を有効にする
description: クラウドで提供される保護を有効にして、高速かつ高度な保護機能を利用できます。
keywords: Microsoft Defender ウイルス対策、マルウェア対策、セキュリティ、クラウド、一目でブロック
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572059"
---
# <a name="turn-on-cloud-delivered-protection"></a>クラウドによる保護を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Microsoft Defender ウイルス対策 クラウド サービスは、ネットワークとエンドポイントに最新の保護を提供するためのメカニズムです。 クラウド サービスと呼ばれますが、クラウドに保存されているファイルを保護するだけではありません。むしろ、分散リソースと機械学習を使用して、従来のセキュリティ インテリジェンス更新プログラムよりもはるかに高速な速度でエンドポイントに保護を提供します。

Microsoft Defender ウイルス対策は、複数の検出および防止技術を使用して、正確でリアルタイムでインテリジェントな保護を実現します。 [エンドポイントの次世代保護のためのマイクロソフトディフェンダーの中核にある高度な技術を知る](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。

クラウドで提供される保護Microsoft Defender ウイルス対策オンまたはオフにするには、次の複数の方法があります。

- Microsoft Intune
- Microsoft エンドポイント マネージャー
- グループ ポリシー
- コマンドレット。

 Windows セキュリティ アプリを使用して、個々のクライアントでオンまたはオフにすることもできます。

クラウド[で提供される保護の概要については、「Microsoft クラウド配信](cloud-protection-microsoft-defender-antivirus.md)保護を使用する」Microsoft Defender ウイルス対策参照してください。

エンドポイントがクラウドで提供される保護サービスに確実に接続できるようにするための、ネットワーク接続の要件の詳細については、「 [ネットワーク接続の構成と検証](configure-network-connections-microsoft-defender-antivirus.md)」を参照してください。

> [!NOTE]
> Windows 10では、このトピックで説明する **基本** レポートオプションと **詳細** レポート オプションの違いはありません。 これは従来の区別であり、どちらかの設定を選択すると、クラウドで提供される保護のレベルが同じになります。 共有される情報の種類や量に違いはありません。 収集内容の詳細については、 [Microsoft のプライバシーに関する声明](https://go.microsoft.com/fwlink/?linkid=521839)を参照してください。

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Intune を使用してクラウドで提供される保護を有効にする

1. Microsoft エンドポイント マネージャー管理センター ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) に移動してログインします。

2. ホーム **ウィンドウで** 、[ **デバイス構成> プロファイル**] を選択します。

3. 構成する **デバイス制限プロファイルの** 種類を選択します。 新しい **デバイス制限** プロファイル タイプを作成する必要がある場合は [、Microsoft Intuneでデバイス制限設定を構成するを](/intune/device-restrictions-configure)参照してください。

4. [**プロパティ**  >  **構成設定:**  >  **編集] Microsoft Defender ウイルス対策** を選択します。

5. クラウド配信保護スイッチ **で** 、[ **有効**] を選択します。

6. [ **サンプル送信前にユーザーに確認** する] ドロップダウンで、[ **すべてのデータを自動的に送信する**] を選択します。

Intune デバイス プロファイルの作成方法と構成方法など、Intune デバイス プロファイルの詳細については、「[デバイス プロファイルのMicrosoft Intuneとは」](/intune/device-profiles)を参照してください。

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Microsoft エンドポイント マネージャーを使用してクラウドで提供される保護を有効にする

1. Microsoft エンドポイント マネージャー管理センター ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) に移動してログインします。

2. **[エンドポイント セキュリティ**  >  **アンチウイルス]** を選択します。

3. ウイルス対策プロファイルを選択します。 (まだプロファイルがない場合、または新しいプロファイルを作成する場合は[、「Microsoft Intuneでデバイス制限の設定を構成](/intune/device-restrictions-configure)する」を参照してください。

4. [ **プロパティ ] を** 選択します。 次に、[ **構成の設定**] の横にある [ **編集**] をクリックします。

5. [ **クラウド保護**] を展開し、[ **クラウドで提供される保護レベル]** の一覧で、次のいずれかを選択します。
   - **高**: 検出の強力なレベルを適用します。
   - **高プラス**: **High** レベルを使用し、追加の保護手段を適用します (クライアントのパフォーマンスに影響を与える可能性があります)。
   - **ゼロ許容範囲**: 不明な実行可能ファイルをすべてブロックします。

6. [ **レビュー + 保存**] を選択し、[ 保存 **]** を選択します。

Microsoft Endpoint Configuration Managerの構成の詳細については、「[マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)」を参照してください。

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>グループ ポリシーを使用してクラウドで配信される保護を有効にする

1. グループ ポリシー管理デバイスで、[グループ [ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))] を開き、構成するグループ ポリシー オブジェクトを右クリックして [ **編集**] を選択します。

2. グループ **ポリシー管理エディタ** で、[コンピュータの **構成]** に移動します。

3. [ **管理用テンプレート**] を選択します。

4. ツリーを展開して **コンポーネントをマップ> Microsoft Defender ウイルス対策 > Windows**

5. [ **マイクロソフトマップに参加**] をダブルクリックします。 オプションがオンになっていることを確認し、基本 **MAPS** または **高度なマップ** に設定します。 **[OK]** を選択します。

6. **[詳細な分析が必要な場合は、ファイル サンプルを送信** する] をダブルクリックします。 最初のオプションが **[有効]** に設定され、他のオプションがどちらかに設定されていることを確認します。

    1. **安全なサンプルを送信** する (1)
    2. **すべてのサンプルを送信** する (3)

        >[!NOTE]
        > [ **安全なサンプルを送信** する (1)] オプションは、ほとんどのサンプルが自動的に送信されることを意味します。 個人情報が含まれている可能性のあるファイルは、引き続きプロンプトを表示し、追加の確認が必要です。
        > オプションを **常にプロンプト** (0) に設定すると、デバイスの保護状態が低下します。 **[送信しない**] (2) に設定すると、エンドポイントの Microsoft Defender の [[一目でブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md)] 機能が機能しません。

7. **[OK]** を選択します。

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>PowerShell コマンドレットを使用してクラウドで提供される保護を有効にする

次のコマンドレットは、クラウドで提供される保護を有効にすることができます。

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については[、「PowerShell コマンドレットを使用してMicrosoft Defender ウイルス対策および](use-powershell-cmdlets-microsoft-defender-antivirus.md) [Defender コマンドレット](/powershell/module/defender/)を構成および実行する」を参照してください。 [ポリシー CSP - ディフェンダー](/windows/client-management/mdm/policy-csp-defender) には、特に [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent)に関する詳細情報もあります。

>[!NOTE]
> また **、-SubmitSamplesConsent** を `SendSafeSamples` (既定の設定 `NeverSend` )、または に設定することもできます `AlwaysPrompt` 。 この `SendSafeSamples` 設定は、ほとんどのサンプルが自動的に送信されることを意味します。 個人情報が含まれている可能性のあるファイルは、引き続きプロンプトを表示し、追加の確認が必要です。

>[!WARNING]
> **設定 -SubmitSamples同意** デバイス `NeverSend` `AlwaysPrompt` の保護レベルを下げるか、または下げます。 さらに、 `NeverSend` エンドポイントの Microsoft Defender の [最初のサイトでブロック](configure-block-at-first-sight-microsoft-defender-antivirus.md) 機能が機能しないことを意味するように設定します。

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Windows管理命令 (WMI) を使用してクラウドで提供される保護を有効にする

次のプロパティ [に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference)クラスの Set メソッドを使用します。

```WMI
MAPSReporting
SubmitSamplesConsent
```

許可されるパラメーターの詳細については[、「WMIv2 API のWindows Defender」を](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)参照してください。

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Windows セキュリティ アプリを使用して、個々のクライアントでクラウド配信保護を有効にする

> [!NOTE]
> [Microsoft MAPS グループ ポリシー **のレポート用にローカル設定の上書きを構成** する] 設定が **[無効]** に設定されている場合、Windows 設定の **クラウドベースの保護** 設定はグレー表示され、使用できなくなります。 グループ ポリシーを使った変更は、Windows の設定で設定を更新する前に、最初に個別のエンドポイントに展開する必要があります。

1. タスクバーで盾アイコンを選択するか、または **[Defender]** のスタートメニューを検索して、Windows セキュリティアプリを開きます。

2. **[ウイルス&脅威対策**] タイル (または左側のメニュー バーの盾アイコン) を選択し、[**ウイルス&脅威対策設定**] ラベルを選択します。

    ![Windows セキュリティ アプリの [ウイルスと脅威の防止の設定] ラベルのスクリーンショット](images/defender/wdav-protection-settings-wdsc.png)

3. **クラウドベースの保護** と **自動サンプル提出** が **On** に切り替わったことを確認します。

> [!NOTE]
> 自動サンプル送信がグループ ポリシーで構成されている場合、設定はグレー表示され、使用できなくなります。

## <a name="related-articles"></a>関連記事

- [クラウド ブロックのタイムアウト期間の構成](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [一目でブロックを構成する](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [PowerShell コマンドレットを使った Microsoft Defender ウイルス対策の管理](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Microsoft Intune用Windows Endpoint Protectionを使用してPCを保護する](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Defender コマンドレット](/powershell/module/defender/)
- [マイクロソフトクラウド配信の保護をMicrosoft Defender ウイルス対策で使用する](cloud-protection-microsoft-defender-antivirus.md)
- [マルウェア対策ポリシーを作成して展開する方法: クラウド保護サービス](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
