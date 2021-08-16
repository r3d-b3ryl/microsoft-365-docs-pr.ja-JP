---
title: Microsoft Defender ウイルス対策によって検出された脅威
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: ウイルス、マルウェアMicrosoft Defender ウイルス対策スパイウェアWindowsソフトウェアの脅威からデバイスを保護する方法について学習します。
ms.openlocfilehash: 79ec44a44c3939a4a868b98d75ab4f24eaf949fcd9bbafb7c0a3173e267f4680
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53896305"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策によって検出された脅威

Microsoft Defender ウイルス対策、マルウェアWindowsスパイウェアなどのソフトウェアの脅威からデバイスを保護します。

- ウイルスは通常、デバイスまたはネットワーク上の他のファイルにコードを添付して拡散し、感染したプログラムが正しく動作しない可能性があります。
- マルウェアには、悪意のあるファイル、アプリケーション、およびコードが含まれます。これは、デバイスの損傷や通常の使用を妨害する可能性があります。 また、マルウェアは、承認されていないアクセスを許可したり、システム リソースを使用したり、パスワードやアカウント情報を盗んだり、コンピューターからロックアウトしたり、身代金を求めるなどできます。
- スパイウェアは、Web 閲覧アクティビティなどのデータを収集し、リモート サーバーにデータを送信します。
 
脅威の保護を提供するために、Microsoft Defender ウイルス対策いくつかの方法を使用します。 これらの方法には、クラウドによる保護、リアルタイム保護、専用の保護更新プログラムが含まれます。

- クラウドによって提供される保護は、新しい脅威や新たな脅威のほぼ瞬時の検出とブロックを提供するのに役立ちます。
- 常時スキャンでは、ファイルとプロセス動作の監視などの手法 (リアルタイム保護とも呼ばれる) *を使用します*。
- 専用の保護更新プログラムは、機械学習、人間および自動のビッグ データ分析、および詳細な脅威耐性の調査に基づいて行います。 

マルウェアとマルウェアの詳細についてはMicrosoft Defender ウイルス対策記事を参照してください。 

- [マルウェアと他&について](/windows/security/threat-protection/intelligence/understanding-malware)
- [Microsoft がマルウェアと望ましくない可能性のあるアプリケーションを特定する方法](/windows/security/threat-protection/intelligence/criteria)
- [Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Microsoft 以外のウイルス対策ソリューションを使用すると、何が起こりますか? 

Microsoft Defender ウイルス対策はオペレーティング システムの一部であり、オペレーティング システムで実行されているデバイスWindows 10。 ただし、Microsoft 以外のウイルス対策ソリューションを使用しているが[、Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用していない場合は、Microsoft Defender ウイルス対策無効モードになります。  

無効モードの場合、ユーザーと顧客は、スケジュールMicrosoft Defender ウイルス対策オンデマンド スキャンで脅威を識別するために、引き続きユーザーとユーザーを使用できます。ただし、Microsoft Defender ウイルス対策は無効です。

- を既定のウイルス対策アプリとして使用できます。
- ファイルを積極的にスキャンして脅威を検出します。
- 脅威を修復または解決します。

Microsoft 以外のウイルス対策ソリューションをアンインストールすると、Microsoft Defender ウイルス対策デバイスを脅威から保護するために自動的にアクティブ モードWindowsされます。

> [!TIP]
> - アプリを使用している場合はMicrosoft 365ウイルス対策ソリューションとしてMicrosoft Defender ウイルス対策を検討してください。 統合は、より良い保護を提供できます。 「[一緒にもっと良い:Microsoft Defender ウイルス対策とOffice 365」 を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)。
> - Microsoft 以外のウイルスMicrosoft Defender ウイルス対策を使用している場合でも、常に最新の状態に保つ必要があります。

## <a name="what-to-expect-when-threats-are-detected"></a>脅威が検出された場合に期待する機能

ユーザーが脅威を検出Microsoft Defender ウイルス対策、次のことが発生します。

- ユーザーはユーザー[に通知を受け取Windows。](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e) 
- 検出は、[保護履歴] ページ [Windows セキュリティアプリ](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)の **一覧に表示** されます。  
- Windows 10 デバイスをセキュリティで保護し[、Intune](/mem/intune/enrollment/windows-enrollment-methods)に登録し、組織に 800 以下のデバイスが登録されている場合は、[脅威とウイルス対策] ページの Microsoft 365 管理センター に脅威<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a>の検出と分析情報が表示されます。これは、ホーム ページの[Microsoft Defender ウイルス対策](secure-win-10-pcs.md)カード (または [正常性の脅威& ウイルス対策] を選択してナビゲーション ウィンドウからアクセスできます。   >  

    組織に Intune に登録されているデバイスが 800 台を超えている場合は、[脅威とウイルス対策] ページではなく[、Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview)からの脅威の検出と分析情報を表示するように求められます。
 
    > [!NOTE]
    > カード **Microsoft Defender ウイルス対策** 脅威とウイルス対策ページは段階的に展開されています。そのため、すぐにアクセスできない場合があります。

ほとんどの場合、ユーザーはそれ以上のアクションを実行する必要はありません。 悪意のあるファイルまたはプログラムがデバイスで検出されるとすぐに、Microsoft Defender ウイルス対策ブロックし、実行を妨げる可能性があります。 さらに、新たに検出された脅威がウイルス対策およびマルウェア対策エンジンに追加され、他のデバイスやユーザーも保護されます。  

悪意のあるファイルの削除の承認など、ユーザーが実行する必要があるアクションがある場合は、ユーザーが受け取った通知に表示されます。 ユーザーに代わって実行Microsoft Defender ウイルス対策アクション、またはユーザーが実行する必要があるアクションの詳細については、「Protection [History」を参照してください](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)。 IT プロフェッショナル/管理者として脅威検出を管理する方法については、「検出された脅威を確認してアクションを実行する」 [を参照してください](review-threats-take-action.md)。

さまざまな脅威の詳細については、「Microsoft セキュリティ インテリジェンス<a href="https://www.microsoft.com/wdsi/threats" target="_blank">脅威</a>」サイトを参照してください。ここで、次のアクションを実行できます。 

- トップの脅威に関する現在の情報を表示します。
- 特定の地域の最新の脅威を表示します。
- 特定の脅威の詳細については、脅威百科事典を検索します。

## <a name="related-content"></a>関連コンテンツ

[デバイスWindows 10セキュリティで保護](secure-windows-10-devices.md)する (記事)\
[評価Microsoft Defender ウイルス対策](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus)(記事)\
[リアルタイムおよびクラウド配信のウイルス対策保護](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) を有効にする方法 (記事)\
[アプリを有効にし、Microsoft Defender ウイルス対策をWindows セキュリティする](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)方法 (記事)\
[グループ ポリシーを使用してMicrosoft Defender ウイルス対策を有効にする](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender)方法 (記事)\
[ウイルス対策定義を更新する方法](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (記事)\
[分析のためにマルウェアとマルウェア以外のマルウェアを Microsoft に送信する](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) 方法 (記事)
