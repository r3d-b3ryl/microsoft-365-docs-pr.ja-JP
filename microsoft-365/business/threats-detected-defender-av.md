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
description: Microsoft Defender Antivirus が、ウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威から Windows デバイスを保護する方法について説明します。
ms.openlocfilehash: ce88e4f7b1caf3a98ebd6dc56d66f0d0fc99a9ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912432"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策によって検出された脅威

Microsoft Defender Antivirus は、ウイルス、マルウェア、スパイウェアなどのソフトウェアの脅威から Windows デバイスを保護します。

- ウイルスは通常、デバイスまたはネットワーク上の他のファイルにコードを添付して拡散し、感染したプログラムが正しく動作しない可能性があります。
- マルウェアには、悪意のあるファイル、アプリケーション、およびコードが含まれます。これは、デバイスの損傷や通常の使用を妨害する可能性があります。 また、マルウェアは、承認されていないアクセスを許可したり、システム リソースを使用したり、パスワードやアカウント情報を盗んだり、コンピューターからロックアウトしたり、身代金を求めるなどできます。
- スパイウェアは、Web 閲覧アクティビティなどのデータを収集し、リモート サーバーにデータを送信します。
 
脅威の保護を提供するために、Microsoft Defender ウイルス対策はいくつかの方法を使用します。 これらの方法には、クラウドによる保護、リアルタイム保護、専用の保護更新プログラムが含まれます。

- クラウドによって提供される保護は、新しい脅威や新たな脅威のほぼ瞬時の検出とブロックを提供するのに役立ちます。
- 常時スキャンでは、ファイルとプロセス動作の監視などの手法 (リアルタイム保護とも呼ばれる) *を使用します*。
- 専用の保護更新プログラムは、機械学習、人間および自動のビッグ データ分析、および詳細な脅威耐性の調査に基づいて行います。 

マルウェアと Microsoft Defender ウイルス対策の詳細については、次の記事を参照してください。 

- [マルウェアと他&について](/windows/security/threat-protection/intelligence/understanding-malware)
- [Microsoft がマルウェアと望ましくない可能性のあるアプリケーションを特定する方法](/windows/security/threat-protection/intelligence/criteria)
- [Windows 10 の次世代保護](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Microsoft 以外のウイルス対策ソリューションを使用すると、何が起こりますか? 

Microsoft Defender Antivirus はオペレーティング システムの一部であり、Windows 10 を実行しているデバイスで有効になっています。 ただし、Microsoft 以外のウイルス対策ソリューションを使用し [、Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用していない場合、Microsoft Defender ウイルス対策は自動的に無効モードになります。  

無効モードの場合でも、ユーザーと顧客は Microsoft Defender ウイルス対策を使用して、スケジュールされたスキャンまたはオンデマンド スキャンを実行して脅威を特定できます。ただし、Microsoft Defender Antivirus は次の機能を使用しなくなりました。

- を既定のウイルス対策アプリとして使用できます。
- ファイルを積極的にスキャンして脅威を検出します。
- 脅威を修復または解決します。

Microsoft 以外のウイルス対策ソリューションをアンインストールすると、Microsoft Defender Antivirus は自動的にアクティブ モードに切り替え、Windows デバイスを脅威から保護します。

> [!TIP]
> - Microsoft 365 を使用している場合は、プライマリ ウイルス対策ソリューションとして Microsoft Defender ウイルス対策を使用してください。 統合は、より良い保護を提供できます。 「Better [together: Microsoft Defender Antivirus and Office 365」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)。
> - Microsoft 以外のウイルス対策ソリューションを使用している場合でも、Microsoft Defender ウイルス対策を最新の状態に保つ必要があります。

## <a name="what-to-expect-when-threats-are-detected"></a>脅威が検出された場合に期待する機能

Microsoft Defender Antivirus によって脅威が検出されると、次のことが発生します。

- ユーザーは Windows [で通知を受け取る](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)。 
- 検出は、[保護の履歴] ページ [の Windows セキュリティ](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)**アプリに一覧表示** されます。  
- [Windows 10](secure-win-10-pcs.md)デバイスをセキュリティで保護して [Intune](/mem/intune/enrollment/windows-enrollment-methods)に登録し、組織に 800 台以下のデバイスが登録されている場合は、[脅威とウイルス対策] ページの Microsoft <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365</a>管理センターに脅威の検出と分析情報が表示されます。この情報は、ホームページの **Microsoft Defender Antivirus** カード (または [正常性の脅威& ウイルス対策] を選択してナビゲーション ウィンドウからアクセスできます。  >  

    組織に Intune に登録されているデバイスが 800 台を超えている場合は、[脅威とウイルス対策] ページではなく[、Microsoft Endpoint Manager](/mem/endpoint-manager-overview)から脅威の検出と分析情報を表示するように求められます。
 
    > [!NOTE]
    > **Microsoft Defender ウイルス対策** カードと **脅威** とウイルス対策ページは段階的に展開され、すぐにアクセスできない場合があります。

ほとんどの場合、ユーザーはそれ以上のアクションを実行する必要はありません。 悪意のあるファイルまたはプログラムがデバイスで検出されるとすぐに、Microsoft Defender Antivirus はデバイスをブロックし、実行を妨げる。 さらに、新たに検出された脅威がウイルス対策およびマルウェア対策エンジンに追加され、他のデバイスやユーザーも保護されます。  

悪意のあるファイルの削除の承認など、ユーザーが実行する必要があるアクションがある場合は、ユーザーが受け取った通知に表示されます。 Microsoft Defender Antivirus がユーザーに代わって実行するアクション、またはユーザーが実行する必要があるアクションの詳細については、「Protection [History」を参照してください](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)。 IT プロフェッショナル/管理者として脅威検出を管理する方法については、「検出された脅威を確認してアクションを実行する」 [を参照してください](review-threats-take-action.md)。

さまざまな脅威について詳しくは <a href="https://www.microsoft.com/wdsi/threats" target="_blank">、Microsoft セキュリティ</a>インテリジェンス脅威サイトをご覧ください。ここで、次のアクションを実行できます。 

- トップの脅威に関する現在の情報を表示します。
- 特定の地域の最新の脅威を表示します。
- 特定の脅威の詳細については、脅威百科事典を検索します。

## <a name="related-content"></a>関連コンテンツ

[Windows 10 デバイスのセキュリティ保護](secure-windows-10-devices.md) (記事)\
[Microsoft Defender ウイルス対策の評価](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (記事)\
[リアルタイムおよびクラウド配信のウイルス対策保護](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) を有効にする方法 (記事)\
[Windows セキュリティ アプリから Microsoft Defender ウイルス対策を有効](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) にし、使用する方法 (記事)\
[グループ ポリシーを使用して Microsoft Defender ウイルス対策を](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) 有効にする方法 (記事)\
[ウイルス対策定義を更新する方法](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (記事)\
[分析のためにマルウェアとマルウェア以外のマルウェアを Microsoft に送信する](../security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis.md) 方法 (記事)