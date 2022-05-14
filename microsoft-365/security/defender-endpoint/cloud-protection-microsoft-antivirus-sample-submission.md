---
title: Microsoft Defender ウイルス対策でのクラウド保護とサンプルの送信
description: クラウド配信の保護とMicrosoft Defender ウイルス対策について説明します
keywords: Microsoft Defender ウイルス対策、次世代テクノロジ、ウイルス対策サンプル送信、次世代 AV、機械学習、マルウェア対策、セキュリティ、Defender、クラウド、クラウド配信保護
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 02/24/2022
ms.collection: M365-security-compliance
ms.openlocfilehash: 08f8e0c861bfd19f11c5b011d0a8db41ce3e73bc
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65419948"
---
# <a name="cloud-protection-and-sample-submission-at-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策でのクラウド保護とサンプルの送信

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策では、マルウェアを検出するための多くのインテリジェントなメカニズムが使用されます。 最も強力な機能の 1 つは、クラウドの能力を適用してマルウェアを検出し、迅速な分析を実行する機能です。 クラウド保護と自動サンプル送信は、Microsoft Defender ウイルス対策と連携して、新しい脅威や新たな脅威から保護するのに役立ちます。 

疑わしいファイルまたは悪意のあるファイルが検出された場合は、分析のためにサンプルがクラウド サービスに送信され、ファイルMicrosoft Defender ウイルス対策ブロックされます。 決定が行われるとすぐに、ファイルはMicrosoft Defender ウイルス対策によって解放またはブロックされます。 

この記事では、クラウド保護の概要と、Microsoft Defender ウイルス対策での自動サンプル送信について説明します。 クラウド保護の詳細については、「[クラウド保護とMicrosoft Defender ウイルス対策](cloud-protection-microsoft-defender-antivirus.md)」を参照してください。

## <a name="how-cloud-protection-and-sample-submission-work-together"></a>クラウド保護とサンプル送信の連携方法

クラウド保護とサンプル送信の連携方法を理解するには、Defender for Endpoint が脅威から保護する方法を理解しておくと役立ちます。 Microsoft Intelligent Security Graphは、センサーの膨大なネットワークからの脅威データを監視します。 Microsoft では、クライアントからの信号とインテリジェント セキュリティ Graph内のセンサーとデータの膨大なネットワークに基づいてファイルを評価できるクラウドベースの機械学習モデルをレイヤー化しています。 このアプローチにより、Defender for Endpoint は、これまでに見たことがない多くの脅威をブロックできます。 

次の図は、Microsoft Defender ウイルス対策を使用したクラウド保護とサンプル送信のフローを示しています。

:::image type="content" source="images/cloud-protection-flow.png" alt-text="クラウド配信の保護フロー" lightbox="images/cloud-protection-flow.png":::

Microsoft Defender ウイルス対策とクラウド保護は、次の方法を使用して、一目で見たことがない新しい脅威を自動的にブロックします。

1. クライアント ベースの機械学習モデルを軽量にし、新しいマルウェアと不明なマルウェアをブロックします。

2. ローカルの動作分析。ファイルベースの攻撃とファイルレス攻撃を停止します。

3. 汎用的およびヒューリスティックな手法を使用して一般的なマルウェアを検出する、高精度のウイルス対策。

4. エンドポイントで実行されているMicrosoft Defender ウイルス対策が、疑わしいファイルの意図を検証するためにより多くのインテリジェンスを必要とする場合に、高度なクラウドベースの保護が提供されます。

   1. Microsoft Defender ウイルス対策明確な決定を行えない場合、ファイル メタデータはクラウド保護サービスに送信されます。 多くの場合、ミリ秒単位で、クラウド保護サービスは、ファイルが悪意のあるものかどうかに関するメタデータに基づいて判断できます。  

      - ファイル メタデータのクラウド クエリは、動作、Web のマーク、または明確な判定が決定されないその他の特性の結果である可能性があります。
      - 小さなメタデータ ペイロードが送信され、脅威ではなくマルウェアの判定に達することを目標としています。 メタデータには、個人を特定できる情報 (PII) は含まれません。 ファイル名などの情報はハッシュされます。
      - 同期または非同期を指定できます。 同期の場合、クラウドが判定をレンダリングするまで、ファイルは開かなくなります。 非同期の場合、クラウド保護によって分析が実行されている間、ファイルが開きます。
      - メタデータには、PE 属性、静的ファイル属性、動的属性とコンテキスト属性などを含めることができます ( [クラウド保護サービスに送信されるメタデータの例を](#examples-of-metadata-sent-to-the-cloud-protection-service)参照)。

   2. メタデータを調べた後、クラウド保護Microsoft Defender ウイルス対策決定的な判定に達できない場合は、さらなる検査のためにファイルのサンプルを要求できます。 この要求は、サンプル送信の設定構成に従います。

      1. **安全なサンプルを自動的に送信する** (既定)
         - セーフサンプルは、.bat、.scr、.dll、.exeなどの PII データが一般的に含まれていないと見なされるサンプルです。
         - ファイルに PII が含まれている可能性が高い場合、ユーザーはファイル サンプルの提出を許可する要求を受け取ります。
         - このオプションは、Windows、macOS、Linux の既定値です。

      2. **常にプロンプトを表示する**
         - 構成されている場合、ユーザーは常にファイルの送信前に同意を求められます
         - この設定は、クラウド保護macOSでは使用できません

      3. **すべてのサンプルを自動的に送信する**
         - 構成されている場合、すべてのサンプルが自動的に送信されます
         - サンプル提出に Word ドキュメントに埋め込まれたマクロを含める場合は、[すべてのサンプルを自動的に送信] を選択する必要があります。
         - この設定は、クラウド保護macOSでは使用できません

      4. **送信しない**
         - ファイル サンプル分析に基づいて "一目でブロック" を防止する
         - "送信しない" は、macOS ポリシーの "無効" 設定に相当します
         - サンプル送信が無効になっている場合でも、検出のためにメタデータが送信されます

   3. メタデータやファイルをクラウド保護に送信した後、 **サンプル**、 **爆発**、または **ビッグ データ分析** 機械学習モデルを使用して、判定に達することができます。 クラウド配信の保護を無効にすると、分析は、ローカルの機械学習モデルや同様の機能を通じてクライアントが提供できるもののみに制限されます。

> [!IMPORTANT]
> [一目でブロック (BAFS)](configure-block-at-first-sight-microsoft-defender-antivirus.md) を使用すると、ファイルまたはプロセスが安全かどうかを判断するための爆発と分析が提供されます。 BAFS は、判定に達するまでファイルの開きを一時的に遅らせることができます。 サンプル送信を無効にすると、BAFS も無効になり、ファイル分析はメタデータのみに制限されます。 サンプル提出と BAFS を有効にしておくことをお勧めします。 詳細については、「[一目でブロックする」を](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)参照してください。

## <a name="cloud-protection-levels"></a>クラウド保護レベル

クラウド保護は、既定でMicrosoft Defender ウイルス対策で有効になっています。 組織の保護レベルは構成できますが、クラウド保護を有効にしておくことをお勧めします。 [「Microsoft Defender ウイルス対策のクラウド配信保護レベルを指定する」を](specify-cloud-protection-level-microsoft-defender-antivirus.md)参照してください。

## <a name="sample-submission-settings"></a>サンプル送信設定

クラウド保護レベルの構成に加えて、サンプル送信設定を構成することもできます。 いくつかのオプションから選択できます。

- **安全なサンプルを自動的に送信**  する (既定の動作)
- **すべてのサンプルを自動的に送信する**  
- **サンプルを送信しない**  

Intune、Configuration Manager、GPO、または PowerShell を使用した構成オプションの詳細については、「[Microsoft Defender ウイルス対策でクラウド保護を有効にする」](enable-cloud-protection-microsoft-defender-antivirus.md)を参照してください。

## <a name="examples-of-metadata-sent-to-the-cloud-protection-service"></a>クラウド保護サービスに送信されるメタデータの例

:::image type="content" source="images/cloud-protection-metadata-sample.png" alt-text="Microsoft Defender ウイルス対策 ポータルでクラウド保護に送信されるメタデータの例" lightbox="images/cloud-protection-metadata-sample.png":::

次の表に、クラウド保護によって分析のために送信されたメタデータの例を示します。

| Type | 属性 |
|:---|:---|
| マシン属性 | `OS version` <br/> `Processor` <br/> `Security settings` |
| 動的属性とコンテキスト属性 | **プロセスとインストール** <br/> `ProcessName` <br/> `ParentProcess` <br/> `TriggeringSignature` <br/> `TriggeringFile` <br/> `Download IP and url` <br/> `HashedFullPath` <br/> `Vpath` <br/> `RealPath` <br/> `Parent/child relationships` <br/><br/>**動作** <br/> `Connection IPs` <br/> `System changes` <br/> `API calls` <br/> `Process injection` <br/><br/>**Locale** <br/> `Locale setting` <br/> `Geographical location` |
| 静的ファイル属性 | **部分ハッシュと完全ハッシュ** <br/> `ClusterHash` <br/> `Crc16` <br/> `Ctph` <br/> `ExtendedKcrcs` <br/> `ImpHash` <br/> `Kcrc3n` <br/> `Lshash` <br/> `LsHashs` <br/> `PartialCrc1` <br/> `PartialCrc2` <br/> `PartialCrc3` <br/> `Sha1` <br/> `Sha256` <br/><br/>**ファイルのプロパティ** <br/>`FileName` <br/> `FileSize` <br/><br/> **署名者情報** <br/> `AuthentiCodeHash` <br/> `Issuer` <br/> `IssuerHash` <br/> `Publisher` <br/> `Signer` <br/> `SignerHash` |

## <a name="samples-are-treated-as-customer-data"></a>サンプルは顧客データとして扱われます

サンプルの提出で何が起こるか気になる場合に備えて、Defender for Endpoint はすべてのファイル サンプルを顧客データとして扱います。 Microsoft は、Defender for Endpoint へのオンボード時に組織が選択した地理的およびデータ保持の選択肢の両方を尊重します。 

さらに、Defender for Endpoint は複数のコンプライアンス認定を受け、高度なコンプライアンス 管理セットへの継続的な準拠を示しています。

- ISO 27001
- ISO 27018
- SOC I、II、III
- PCI

詳細については、以下のリソースをご覧ください。

- [Azure コンプライアンス オファリング](/azure/storage/common/storage-compliance-offerings) 
- [Service Trust Portal](https://servicetrust.microsoft.com)
- [データストレージとプライバシーをMicrosoft Defender for Endpointする](data-storage-privacy.md#data-storage-location)

## <a name="other-file-sample-submission-scenarios"></a>その他のファイル サンプル提出シナリオ

Defender for Endpoint が、Microsoft Defender ウイルス対策でのクラウド保護に関連しないファイル サンプルを要求するシナリオは、さらに 2 つあります。 これらのシナリオについては、次の表で説明します。

| シナリオ | 説明 |
|:---|:---|
|Microsoft 365 Defender ポータルでの手動ファイル サンプル コレクション | デバイスを Defender for Endpoint にオンボードするときに、[エンドポイントでの検出と対応 (EDR)](overview-endpoint-detection-response.md) の設定を構成できます。 たとえば、デバイスからのサンプル コレクションを有効にする設定があります。これは、この記事で説明するサンプル送信設定と簡単に混同される可能性があります。 <br/><br/>EDR設定は、Microsoft 365 Defender ポータルを介して要求されたときにデバイスからのファイル サンプル コレクションを制御し、既に確立されているロールとアクセス許可の対象となります。 この設定では、Microsoft 365 Defender ポータルでの詳細分析などの機能について、エンドポイントからのファイル収集を許可またはブロックできます。 この設定が構成されていない場合、既定ではサンプル コレクションを有効にします。 <br/><br/>Defender for Endpoint 構成設定の詳細については、「[Defender for Endpoint でのWindows 10 デバイスのオンボード ツールとメソッド」を参照してください](configure-endpoints.md)。 |
| 自動調査と応答のコンテンツ分析 | [自動調査](automated-investigations.md)がデバイスで実行されている場合 (アラートに応答して自動的に実行するように構成されている場合、または手動で実行するように構成されている場合)、疑わしいと識別されたファイルをエンドポイントから収集して、詳細な検査を行うことができます。 必要に応じて、Microsoft 365 Defender ポータルで、自動調査用のファイル コンテンツ分析機能を無効にすることができます。 <br/><br/> ファイル拡張子の名前は、自動調査中に自動的に送信される他のファイルの種類の拡張子を追加または削除するように変更することもできます。 <br/><br/> 詳細については、「 [オートメーション ファイルのアップロードの管理](manage-automation-file-uploads.md)」を参照してください。 |

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

[次世代保護の概要](next-generation-protection.md)

[Microsoft Defender ウイルス対策検出の修復を構成します。](configure-remediation-microsoft-defender-antivirus.md)
