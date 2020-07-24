---
title: GDPR および CCPA のための Windows エンタープライズ データ主体要求のデータ プロセッサー サービス
description: Microsoft 製品、サービス、管理ツールを使用して、DSR に応じて個人データを検索して操作する方法について説明します。
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: bc88f8911f44c9c7b8aad8fbecbbeb073fdcb9ba
ms.sourcegitcommit: 209a9963719f1ca85ca2075c02721e1a318a7a13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "45374803"
---
# <a name="data-processor-service-for-windows-enterprise-data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR および CCPA のための Windows エンタープライズ データ主体要求のデータ プロセッサー サービス 

>[!NOTE]
>このトピックは、Windows Enterprise プレビュー プログラム用データプロセッササービスの参加者を対象としており、特定の使用条件に同意することが要求されています。 プログラムの詳細を確認し、使用条件に同意するには、[https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview) を参照してください。

## <a name="introduction-to-data-subject-requests-dsrs"></a>データ主体要求 (DSR) の概要 
EU 一般データ保護規則 (GDPR) は、規制において_データ主体_と呼ばれる人に、雇用主または他の種類の機関や組織 (_データ コントローラー_または単に_コントローラー_と呼ばれます) によって収集された個人データを管理する権限を与えます。 GDPR での個人データは、特定されたまたは特定可能な自然人に関連するすべてのデータと、非常に幅広く定義されています。 GDPR では、個人データに対するデータ主体固有の権限が付与されます。このような権限には、個人データのコピーの取得、個人データの修正の要求、個人データの処理の制限、個人データの削除、または別のコントローラーに移動できる電子的な形式での個人データの受け取りが含まれます。 データ主体がコントローラーに対して個人データへのアクションを実行するよう正式に要求することを、_データ主体の要求_または DSR と呼びます。 

同様に、カリフォルニア州消費者プライバシー法 (CCPA) では、それらの個人情報の削除、アクセスおよび受信 (移植性) の権利などの GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。 また、CCPA では、特定の開示、権利の行使を選択する際の差別に対する保護、“売上“ として分類された特定のデータ転送の “オプトアウト/オプトイン“ 要件を規定します。 「販売」は広く定義されており、有価約因に関するデータの共有を含みます。 CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq)」を参照してください。

このガイドでは、DSR への対応として個人データを見つけて処理するコントローラーのお客様を支援する目的で、Microsoft の製品、サービス、管理ツールをどのように使用できるかを説明します。特に、Microsoft クラウドにある個人データを検出、アクセス、処理する方法を示します。このガイドで説明するプロセスの概要は次のとおりです: 

1. **評価**—Microsoft クラウドにある個人データを取り出し、コピーが要求されている場合には、データ サブジェクトが利用できる形でコピーを作成します。 
2. **削除**—Microsoft クラウドに格納されていた個人データを完全に削除します。 
3. **エクスポート**—個人データの電子的コピー (マシンで読み取り可能な形式) をデータ サブジェクトに提供します。 CCPA における個人情報とは、識別された人、または識別可能な人に関するあらゆる情報のことです。

CCPA における個人情報とは、識別された人、または識別可能な人に関するあらゆる情報のことです。 個人の私的、公的、または職業上の役割による区別はありません。 "個人情報" と定義された用語は、GDPR における "個人データ" とほぼ同義です。 ただし、CCPA では家族データおよび世帯データも含まれます。 CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq)」を参照してください。

このガイドの各セクションでは、Microsoft クラウド内の個人データに関する DSR への対応としてデータ コントローラー組織が実行できる技術的な手順の概要を示します。 

## <a name="terminology"></a>用語集 
このガイドに関連する用語を以下に定義します。 

* _コントローラー_—単独で、または他者と共同で、個人データの処理の目的と手段を決定する個人または法人、公的機関、団体、その他の組織。そのような処理の目的と手段が ＥＵ 法もしくは構成国法によって決定される場合、コントローラーまたはその指名に関する具体的な基準が ＥＵ 法もしくは構成国法によって提供される場合があります。 

* _個人データおよびデータ主体_—特定される個人、または特定可能な個人 ('データ主体') に関連するあらゆる情報であり、特定可能な個人とは、その個人の名前、ID 番号、位置データ、オンライン ID、または物理的、生理学的、遺伝子上、心理的、経済的、文化的、社会的な識別情報に固有の 1 つ以上の因子を参照することによって直接または間接的に特定される人物です。 

* _プロセッサ_—コントローラーに代わって個人データを処理する個人または法人、公的機関、団体、その他の組織。 

* _顧客データ_ - これは、顧客または顧客の代理が エンタープライズ サービスの使用を通じて Microsoft に提供する、テキスト、音声、ビデオ、画像ファイル、およびソフトウェアを含むすべてのデータのことです。 

* _Windows 診断データ_ - Windows デバイスから取得する、デバイスおよび Windows と関連ソフトウェアの実行方法に関する重要な技術データです。 Windows を最新の状態に保ち、セキュリティ、信頼性、パフォーマンスを維持し、Windows の使用状況を総合的に分析して改善するために使用されます。 Windows 診断データのいくつかの例は、使用されているハードウェアの種類、それぞれの使用法でインストールされたアプリケーション、およびデバイス ドライバーの信頼性に関する情報です。 一部の Windows コンポーネントやアプリは Microsoft サービスに直接接続しますが、それらがやり取りするデータは Windows 診断データではありません。 たとえば、ユーザーの現在地を地域の天気やニュースに交換することは、Windows 診断データの例ではありません。 

## <a name="how-to-use-this-guide"></a>このガイドの使用方法 

Windows エンタープライズ登録済みデバイスのデータ プロセッサ サービスを使用すると、Windows はサービスを提供するために、Windows 診断データと呼ばれるいくつかの情報を生成します。

## <a name="windows-diagnostic-data"></a>Windows 診断データ 

Microsoft は、ユーザーによる Windows エンタープライズのデータ プロセッサ サービスの使用に関連する Windows 診断データへのアクセス、削除、およびエクスポートを行う機能を提供します。

>[!IMPORTANT]
>Windows 診断データを修正する機能はサポートされていません。 Windows 診断データは、Windows 内で行われる実際の操作を構成します。そのようなデータへの変更は、操作の履歴記録を危険にさらし、セキュリティのリスクを高め、信頼性を損なう可能性があります。 このドキュメントに記載されているすべてのデータは、Windows 診断データと見なされます。 

## <a name="executing-dsrs-against-windows-diagnostic-data"></a>Windows 診断データに対する DSR の実行 

Microsoft の特定の Windows 診断データにアクセスし、それを削除したりエクスポートしたりするには、Azure ポータルを使用するか、特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) を直接使用できます。

### <a name="step-1-access"></a>手順 1: アクセス 

テナント管理者は、特定のユーザーによる Windows エンタープライズ登録済みデバイスのデータ プロセッサ サービスの使用に関連する Windows 診断データにアクセスできる組織内の唯一の人物です。 アクセス要求に対して取得されるデータは、エクスポートによってコンピューターが読み取り可能な形式で提供され、ユーザーがデータに関連付けられているデバイスとサービスを認識できるファイルで提供されます。 上記で説明したように、取得されるデータには Windows サービスのセキュリティまたは安定性を損なう可能性があるデータは含まれません。 

お客様企業のテナント管理者はポータル エクスペリエンスを利用して、DSR アクセス要求を管理することができます。 「[Azure DSR、パート 2、手順 3: エクスポート](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export)」では、Azure ポータルを介して、エクスポートを介して DSR アクセス要求を実行する方法について説明します。

### <a name="step-2-delete"></a>手順 2: 削除 

Microsoft は、特定のユーザーの Azure Active Directory オブジェクトに基づいてユーザーベースの DSR 削除要求を実行する方法を提供しています。

ユーザーベースの削除要求の場合、お客様企業のテナント管理者はポータル エクスペリエンスを利用して、DSR 削除要求を管理することができます。 「[Azure DSR、パート 1、手順 5: 削除](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-5-delete)」では、Azure ポータルを介して、DSR 削除要求を実行する方法について説明します。 

Microsoft は、既存のアプリケーション プログラミング インターフェイス (API) を介して直接顧客データを削除するユーザーを削除する機能を提供します。 詳細については、「[API 参照ドキュメンテーション](https://docs.microsoft.com/graph/api/directory-deleteditems-delete?view=graph-rest-beta)」に記載されています。 

>[!IMPORTANT]  
>収集したデータを削除しても、それ以上の収集は停止しません。 データ収集をオフにするには、「[各サービスの参照ドキュメント](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)」に記載されている手順に従ってください。
 
 さらに、ユーザーベースの削除要求では、ユーザー アカウント自体を削除する必要があります。 

### <a name="step-3-export"></a>手順 3: エクスポート 

テナント管理者は、特定のユーザーによる Windows エンタープライズ登録済みデバイスのデータ プロセッサ サービスの使用に関連する Windows 診断データにアクセスできる組織内の唯一の人物です。 エクスポート要求に対して取得されるデータは、コンピューターが読み取り可能な形式で提供され、ユーザーがデータに関連付けられているデバイスとサービスを認識できるファイルで提供されます。 上記で説明したように、取得されるデータには Windows サービスのセキュリティまたは安定性を損なう可能性があるデータは含まれません。 「[Azure DSR、パート 2、手順 3: エクスポート](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export)」では、Azure ポータルを介して、DSR エクスポート要求を実行する方法について説明します。 

Microsoft は、既存のアプリケーション プログラミング インターフェイス (API) を介して直接顧客データをエクスポートする機能を提供します。 詳細については、「[API 参照ドキュメンテーション](https://docs.microsoft.com/graph/api/user-exportpersonaldata?view=graph-rest-1.0)」に記載されています。

## <a name="notify-about-exporting-or-deleting-issues"></a>エクスポートまたは削除に関する問題を通知する 

Azure portal でデータをエクスポートまたは削除中に問題が発生した場合は、Azure ポータルの **[ヘルプとサポート]** ブレードに移動し、**[サブスクリプションの管理] > [他のセキュリティとコンプライアンスの要求] > [プライバシー ブレードと GDPR 要求]** で新しいチケットを送信します。 
