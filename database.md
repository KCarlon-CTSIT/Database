CREATE DATABASE  IF NOT EXISTS `ultimau5_atilive` /*!40100 DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci */ /*!80016 DEFAULT ENCRYPTION='N' */;
USE `ultimau5_atilive`;
-- MySQL dump 10.13  Distrib 8.0.46, for Win64 (x86_64)
--
-- Host: 192.168.1.85    Database: ultimau5_atilive
-- ------------------------------------------------------
-- Server version	8.0.46-0ubuntu0.24.04.4

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!50503 SET NAMES utf8 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;

--
-- Table structure for table `BINLOC`
--

DROP TABLE IF EXISTS `BINLOC`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `BINLOC` (
  `BLCode` int NOT NULL AUTO_INCREMENT,
  `BLDescription` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WHCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`BLCode`),
  KEY `WHCode` (`WHCode`),
  CONSTRAINT `BINLOC_ibfk_1` FOREIGN KEY (`WHCode`) REFERENCES `OWHS` (`WhsCode`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=261 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `BaseType`
--

DROP TABLE IF EXISTS `BaseType`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `BaseType` (
  `baseID` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `baseName` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `CATEGORY`
--

DROP TABLE IF EXISTS `CATEGORY`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `CATEGORY` (
  `catID` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `catName` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `CRD1`
--

DROP TABLE IF EXISTS `CRD1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `CRD1` (
  `LineNum` int NOT NULL AUTO_INCREMENT,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `Address` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Street` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Block` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ZipCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `City` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `County` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Country` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `State` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Building` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `AdresType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address2` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address3` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AddrType` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StreetNo` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`LineNum`),
  KEY `CardCode` (`CardCode`),
  CONSTRAINT `CRD1_ibfk_1` FOREIGN KEY (`CardCode`) REFERENCES `OCRD` (`CardCode`) ON DELETE RESTRICT ON UPDATE RESTRICT
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `DEPARTMENT`
--

DROP TABLE IF EXISTS `DEPARTMENT`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `DEPARTMENT` (
  `DEPT_ID` int NOT NULL AUTO_INCREMENT,
  `NAME` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `BUDGET` int NOT NULL,
  `JOBTITLE` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Q1` int NOT NULL,
  `Q2` int NOT NULL,
  `Q3` int NOT NULL,
  `Q4` int NOT NULL,
  `TENANT_ID` int NOT NULL,
  PRIMARY KEY (`DEPT_ID`)
) ENGINE=InnoDB AUTO_INCREMENT=13 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `DLN1`
--

DROP TABLE IF EXISTS `DLN1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `DLN1` (
  `LineNum` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` decimal(6,0) DEFAULT NULL,
  `LineStatus` tinyint(1) NOT NULL DEFAULT '0',
  `ItemCode` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Dscription` varchar(1000) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Y',
  `AcctCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` int NOT NULL DEFAULT '0',
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Text` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DUsage` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PQTReqQty` decimal(19,6) DEFAULT NULL,
  `PQTReqDate` date DEFAULT NULL,
  `PcDocType` decimal(6,0) DEFAULT NULL,
  `PcQuantity` decimal(19,6) DEFAULT NULL,
  `LinManClsd` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatGrpSrc` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`LineNum`),
  KEY `DocEntry` (`DocEntry`),
  CONSTRAINT `DLN1_ibfk_1` FOREIGN KEY (`DocEntry`) REFERENCES `ODLN` (`DocEntry`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=8958 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `DLN11`
--

DROP TABLE IF EXISTS `DLN11`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `DLN11` (
  `LineNum` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` decimal(6,0) DEFAULT NULL,
  `LineStatus` tinyint(1) NOT NULL DEFAULT '0',
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Dscription` varchar(1000) DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` int NOT NULL DEFAULT '0',
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Text` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DUsage` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTReqQty` decimal(19,6) DEFAULT NULL,
  `PQTReqDate` date DEFAULT NULL,
  `PcDocType` decimal(6,0) DEFAULT NULL,
  `PcQuantity` decimal(19,6) DEFAULT NULL,
  `LinManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGrpSrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`LineNum`),
  KEY `DocEntry` (`DocEntry`),
  CONSTRAINT `DLN11_ibfk_1` FOREIGN KEY (`DocEntry`) REFERENCES `ODLN` (`DocEntry`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=4945 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `DLN12`
--

DROP TABLE IF EXISTS `DLN12`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `DLN12` (
  `LineNum` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` decimal(6,0) DEFAULT NULL,
  `LineStatus` tinyint(1) NOT NULL DEFAULT '0',
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Dscription` varchar(1000) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` int NOT NULL DEFAULT '0',
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Text` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DUsage` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTReqQty` decimal(19,6) DEFAULT NULL,
  `PQTReqDate` date DEFAULT NULL,
  `PcDocType` decimal(6,0) DEFAULT NULL,
  `PcQuantity` decimal(19,6) DEFAULT NULL,
  `LinManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGrpSrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`LineNum`),
  KEY `DocEntry` (`DocEntry`),
  CONSTRAINT `FK_DLN12_TO_ODLN2_DocEntD7be1` FOREIGN KEY (`DocEntry`) REFERENCES `ODLN2` (`DocEntry`) ON DELETE RESTRICT ON UPDATE RESTRICT
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `GLdeter`
--

DROP TABLE IF EXISTS `GLdeter`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `GLdeter` (
  `GLdetID` int NOT NULL AUTO_INCREMENT,
  `TypeOfAccount` varchar(150) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctID` int DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctName` varchar(150) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GLType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`GLdetID`)
) ENGINE=InnoDB AUTO_INCREMENT=73 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `IGE1`
--

DROP TABLE IF EXISTS `IGE1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `IGE1` (
  `DocEntry` int NOT NULL,
  `LineNum` int NOT NULL,
  `ItemCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Dscription` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `WhsCode` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `AcctCode` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `OcrCode` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `LineStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`,`LineNum`),
  CONSTRAINT `FK_OIGE_IGE1` FOREIGN KEY (`DocEntry`) REFERENCES `OIGE` (`DocEntry`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `IGN1`
--

DROP TABLE IF EXISTS `IGN1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `IGN1` (
  `DocEntry` int NOT NULL,
  `LineNum` int NOT NULL,
  `TargetType` int DEFAULT NULL,
  `TrgetEntry` int DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `BaseType` int DEFAULT NULL,
  `BaseEntry` int DEFAULT NULL,
  `BaseLine` int DEFAULT NULL,
  `LineStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `ItemCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Dscription` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `CodeBars` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `SerialNum` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT '0.000000',
  `OpenQty` decimal(19,6) DEFAULT '0.000000',
  `InvQty` decimal(19,6) DEFAULT '0.000000',
  `WhsCode` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `FromWhsCod` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'Y',
  `Price` decimal(19,6) DEFAULT '0.000000',
  `PriceBefDi` decimal(19,6) DEFAULT '0.000000',
  `PriceAfVAT` decimal(19,6) DEFAULT '0.000000',
  `Currency` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT '0.000000',
  `DiscPrcnt` decimal(19,6) DEFAULT '0.000000',
  `LineTotal` decimal(19,6) DEFAULT '0.000000',
  `TotalFrgn` decimal(19,6) DEFAULT '0.000000',
  `StockPrice` decimal(19,6) DEFAULT '0.000000',
  `DocDate` date DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `TaxCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `VatGroup` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT '0.000000',
  `VatSum` decimal(19,6) DEFAULT '0.000000',
  `AcctCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `OcrCode` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `OcrCode2` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `UomCode` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` int DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `VisOrder` int DEFAULT NULL,
  `FreeTxt` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci,
  PRIMARY KEY (`DocEntry`,`LineNum`),
  CONSTRAINT `FK_IGN1_OIGN` FOREIGN KEY (`DocEntry`) REFERENCES `OIGN` (`DocEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `IMG`
--

DROP TABLE IF EXISTS `IMG`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `IMG` (
  `imageID` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SourceID` int DEFAULT NULL,
  `name` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `image` longblob,
  `path` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`imageID`)
) ENGINE=InnoDB AUTO_INCREMENT=3880 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `IMGApproval`
--

DROP TABLE IF EXISTS `IMGApproval`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `IMGApproval` (
  `imageID` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SourceID` int DEFAULT NULL,
  `name` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `image` longblob,
  `path` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`imageID`),
  KEY `IMG_Approval_FK_001_idx` (`SourceID`),
  CONSTRAINT `IMG_Approval_FK_001` FOREIGN KEY (`SourceID`) REFERENCES `OWTM` (`WtmCode`)
) ENGINE=InnoDB AUTO_INCREMENT=2696 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `IMGDR`
--

DROP TABLE IF EXISTS `IMGDR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `IMGDR` (
  `imageID` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `DocNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `name` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `image` longblob,
  `path` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`imageID`),
  KEY `DocEntry` (`DocEntry`)
) ENGINE=InnoDB AUTO_INCREMENT=107 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `IMGESR`
--

DROP TABLE IF EXISTS `IMGESR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `IMGESR` (
  `imageID` int NOT NULL AUTO_INCREMENT,
  `SRID` int DEFAULT NULL,
  `EquipmentID` int DEFAULT NULL,
  `name` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `image` longblob,
  `path` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`imageID`),
  KEY `fk_images_oscl` (`SRID`),
  KEY `fk_images_equipment` (`EquipmentID`),
  CONSTRAINT `fk_images_equipment` FOREIGN KEY (`EquipmentID`) REFERENCES `OSCL_EquipmentDetails` (`EquipmentID`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `fk_images_oscl` FOREIGN KEY (`SRID`) REFERENCES `OSCL` (`SRID`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=707 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `IMGPO`
--

DROP TABLE IF EXISTS `IMGPO`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `IMGPO` (
  `imageID` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SourceID` int DEFAULT NULL,
  `name` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `image` longblob,
  `path` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`imageID`)
) ENGINE=InnoDB AUTO_INCREMENT=2698 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `INV1`
--

DROP TABLE IF EXISTS `INV1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `INV1` (
  `DocEntry` int NOT NULL,
  `LineNum` int NOT NULL,
  `ItemCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Dscription` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT '0.000000',
  `ShipDate` date DEFAULT NULL,
  `WhsCode` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT '0.000000',
  `Currency` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT '0.000000',
  `GrossBuyPr` decimal(19,6) DEFAULT '0.000000',
  `StockValue` decimal(19,6) DEFAULT '0.000000',
  `GrssProfit` decimal(19,6) DEFAULT '0.000000',
  `BaseType` int DEFAULT '-1',
  `BaseEntry` int DEFAULT NULL,
  `BaseLine` int DEFAULT NULL,
  `TargetType` int DEFAULT '-1',
  `InvntSttus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'Y',
  `VatGroup` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`,`LineNum`),
  KEY `idx_inv1_item` (`ItemCode`),
  KEY `idx_inv1_whs` (`WhsCode`),
  CONSTRAINT `fk_inv1_oinv` FOREIGN KEY (`DocEntry`) REFERENCES `OINV` (`DocEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `INVTYPE`
--

DROP TABLE IF EXISTS `INVTYPE`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `INVTYPE` (
  `InvTypeCode` int NOT NULL AUTO_INCREMENT,
  `InvTypeName` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`InvTypeCode`)
) ENGINE=InnoDB AUTO_INCREMENT=12 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `ITM1`
--

DROP TABLE IF EXISTS `ITM1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `ITM1` (
  `ItemCount` int NOT NULL AUTO_INCREMENT,
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL DEFAULT '',
  `PriceList` decimal(6,0) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ovrwritten` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Factor` decimal(19,6) DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`ItemCount`)
) ENGINE=InnoDB AUTO_INCREMENT=33685 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `ITM1_temp`
--

DROP TABLE IF EXISTS `ITM1_temp`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `ITM1_temp` (
  `ItemCount` int NOT NULL AUTO_INCREMENT,
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL DEFAULT '',
  `PriceList` decimal(6,0) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ovrwritten` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Factor` decimal(19,6) DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`ItemCount`)
) ENGINE=InnoDB AUTO_INCREMENT=129 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `JDT1`
--

DROP TABLE IF EXISTS `JDT1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `JDT1` (
  `Line_ID` int NOT NULL AUTO_INCREMENT,
  `TransId` int NOT NULL,
  `Account` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Debit` decimal(19,6) DEFAULT NULL,
  `Credit` decimal(19,6) DEFAULT NULL,
  `SYSCred` decimal(19,6) DEFAULT NULL,
  `SYSDeb` decimal(19,6) DEFAULT NULL,
  `FCDebit` decimal(19,6) DEFAULT NULL,
  `FCCredit` decimal(19,6) DEFAULT NULL,
  `FCCurrency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DueDate` date DEFAULT NULL,
  `SourceID` decimal(6,0) DEFAULT NULL,
  `SourceLine` decimal(6,0) DEFAULT NULL,
  `ShortName` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IntrnMatch` decimal(6,0) DEFAULT NULL,
  `ExtrMatch` decimal(6,0) DEFAULT NULL,
  `ContraAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LineMemo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref3Line` varchar(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RefDate` date DEFAULT NULL,
  `Ref2Date` date DEFAULT NULL,
  `Ref1` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref2` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreatedBy` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransCode` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ProfitCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `SystemRate` decimal(19,6) DEFAULT NULL,
  `MthDate` date DEFAULT NULL,
  `ToMthSum` decimal(19,6) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `BatchNum` decimal(6,0) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `RelTransId` decimal(6,0) DEFAULT NULL,
  `RelLineID` decimal(6,0) DEFAULT NULL,
  `RelType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseSum` decimal(19,6) DEFAULT NULL,
  `VatRate` decimal(19,6) DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AdjTran` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `PaymentRef` varchar(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SYSBaseSum` decimal(19,6) DEFAULT NULL,
  `MultMatch` decimal(6,0) DEFAULT NULL,
  `VatLine` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatAmount` decimal(19,6) DEFAULT NULL,
  `SYSVatSum` decimal(19,6) DEFAULT NULL,
  `Closed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossValue` decimal(19,6) DEFAULT NULL,
  `CheckAbs` decimal(6,0) DEFAULT NULL,
  `LineType` decimal(6,0) DEFAULT NULL,
  `DebCred` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SequenceNr` decimal(6,0) DEFAULT NULL,
  `StornoAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BalDueDeb` decimal(19,6) DEFAULT NULL,
  `BalDueCred` decimal(19,6) DEFAULT NULL,
  `BalFcDeb` decimal(19,6) DEFAULT NULL,
  `BalFcCred` decimal(19,6) DEFAULT NULL,
  `BalScDeb` decimal(19,6) DEFAULT NULL,
  `BalScCred` decimal(19,6) DEFAULT NULL,
  `IsNet` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DunWizBlck` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `DunDate` date DEFAULT NULL,
  `TaxType` decimal(6,0) DEFAULT NULL,
  `TaxPostAcc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StaCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StaType` decimal(6,0) DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ValidFrom` date DEFAULT NULL,
  `GrossValFc` decimal(19,6) DEFAULT NULL,
  `LvlUpdDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MIEntry` decimal(6,0) DEFAULT NULL,
  `MIVEntry` decimal(6,0) DEFAULT NULL,
  `ClsInTP` decimal(6,0) DEFAULT NULL,
  `CenVatCom` decimal(6,0) DEFAULT NULL,
  `MatType` decimal(6,0) DEFAULT NULL,
  `PstngType` decimal(6,0) DEFAULT NULL,
  `ValidFrom2` date DEFAULT NULL,
  `ValidFrom3` date DEFAULT NULL,
  `ValidFrom4` date DEFAULT NULL,
  `ValidFrom5` date DEFAULT NULL,
  `Location` decimal(6,0) DEFAULT NULL,
  `WTaxCode` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatRate` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `SYSEquSum` decimal(19,6) DEFAULT NULL,
  `TotalVat` decimal(19,6) DEFAULT NULL,
  `SYSTVat` decimal(19,6) DEFAULT NULL,
  `WTLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTLine` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `PayBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`Line_ID`),
  KEY `TransId` (`TransId`)
) ENGINE=InnoDB AUTO_INCREMENT=706 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `Mst_Refrigerants`
--

DROP TABLE IF EXISTS `Mst_Refrigerants`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `Mst_Refrigerants` (
  `id` int NOT NULL AUTO_INCREMENT,
  `Refrigerant` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `Type` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `SafetyClass` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `GWP_100Year` int DEFAULT NULL,
  `GWP_20Year` int DEFAULT NULL,
  `Applications` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `RegulatoryStatus` varchar(150) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IsActive` tinyint(1) DEFAULT '1',
  `CreatedAt` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  `UpdatedAt` timestamp NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  UNIQUE KEY `Refrigerant` (`Refrigerant`),
  KEY `idx_ref_type` (`Type`)
) ENGINE=InnoDB AUTO_INCREMENT=22 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OACT`
--

DROP TABLE IF EXISTS `OACT`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OACT` (
  `AcctID` int NOT NULL AUTO_INCREMENT,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL DEFAULT '',
  `AcctName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CurrTotal` decimal(19,6) DEFAULT NULL,
  `EndTotal` decimal(19,6) DEFAULT NULL,
  `Finanse` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Groups` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Budget` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Postable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Levels` decimal(6,0) DEFAULT NULL,
  `GrpLine` decimal(6,0) DEFAULT NULL,
  `FatherNum` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AccntntCod` varchar(12) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GroupMask` decimal(6,0) DEFAULT NULL,
  `ActType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActCurr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RealAcct` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocManTran` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CfwRlvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfltVat` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Category` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PrjRelvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`AcctID`)
) ENGINE=InnoDB AUTO_INCREMENT=468 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OADM`
--

DROP TABLE IF EXISTS `OADM`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OADM` (
  `CompnyName` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `CompnyAddr` char(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Country` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PrintHeadr` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Phone1` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Phone2` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Fax` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `E_Mail` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Manager` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CompType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MainCurncy` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SysCurrncy` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DispPosDeb` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DefLengthU` decimal(6,0) DEFAULT NULL,
  `DefWeightU` decimal(6,0) DEFAULT NULL,
  `DfltVendPM` char(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DirectRate` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MinAmnt347` decimal(19,6) DEFAULT NULL,
  `AutoITW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankCountr` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxIdNum` char(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevOffice` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeZoneNo` char(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DdctFileNo` char(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatCharge` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayOutVat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `DpsitPrcnt` decimal(19,6) DEFAULT NULL,
  `IncomeTax` decimal(19,6) DEFAULT NULL,
  `VendorDdct` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CustmrDdct` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DdctPercnt` decimal(19,6) DEFAULT NULL,
  `DdctExpire` date DEFAULT NULL,
  `DdctOffice` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EURepSqntl` decimal(6,0) DEFAULT NULL,
  `BoxRptSeq` decimal(6,0) DEFAULT NULL,
  `WTLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfltCustPM` char(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AllowFuPos` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseProdWip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CurrPeriod` char(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `XmlPath` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DflBnkKey` decimal(6,0) DEFAULT NULL,
  `BSInstled` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseExtRpt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ERpPerType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfSVatExmp` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfPVatExmp` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Manager1` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Manager1F` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CCMask` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ObligLimit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreditLimt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SalesLimit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DlnLimit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrderLimit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AddDlnBlnc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreditDpst` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MultiLang` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DbVers` decimal(6,0) DEFAULT NULL,
  `ApplVers` decimal(6,0) DEFAULT NULL,
  `DflWebSite` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevisionPo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Reindex` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxIdValid` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PchName` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RpcName` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PdnName` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RpdName` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PorName` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LevelWarn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CrdCommUse` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ItmCommUse` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCommUse` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfCustTerm` int DEFAULT NULL,
  `DfVendTerm` int DEFAULT NULL,
  `SaleProfit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CostPrcLst` decimal(6,0) DEFAULT NULL,
  `GrossBySal` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TreePricOn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AddVat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseFld` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ClosedQuot` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseCode` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Code1` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Code2` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Code3` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Code4` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Color` decimal(6,0) DEFAULT NULL,
  `SumDec` decimal(6,0) DEFAULT NULL,
  `QtyDec` decimal(6,0) DEFAULT NULL,
  `PriceDec` decimal(6,0) DEFAULT NULL,
  `RateDec` decimal(6,0) DEFAULT NULL,
  `PercentDec` decimal(6,0) DEFAULT NULL,
  `MeasureDec` decimal(6,0) DEFAULT NULL,
  `DdAutoRun` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DdNextDue` date DEFAULT NULL,
  `DdHour` decimal(6,0) DEFAULT NULL,
  `CmpnyAddrF` char(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DflTaxCode` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PrintHdrF` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Phone1F` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Phone2F` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FaxF` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ManagerF` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TimeFormat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CigCup` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DateFormat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DateSep` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FcNoBlnc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChangeRdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MultiCurr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickParDlv` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `255TaxIncr` decimal(19,6) DEFAULT NULL,
  `ISRType` decimal(6,0) DEFAULT NULL,
  `255TaxDecr` decimal(19,6) DEFAULT NULL,
  `RoundRmrk` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ISRBillerI` char(9) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdStamp` decimal(6,0) DEFAULT NULL,
  `SysCNoEdit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RefDNoEdit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfltWhs` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDNoEdit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfSVatItem` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfSVatServ` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfPVatItem` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfPVatServ` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DoBudget` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CustIdNum` char(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BgtBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BgtWarning` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BdgtPORDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BdgtAcctng` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BdgtDflt` decimal(6,0) DEFAULT NULL,
  `ContInvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `InvntSystm` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ApplicIFRS` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StartYear` decimal(6,0) DEFAULT NULL,
  `According` decimal(6,0) DEFAULT NULL,
  `MltpBrnchs` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EnblSrvTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DftRCN` decimal(6,0) DEFAULT NULL,
  `RoundVat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BdgtPDNDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IRSFileNo` char(9) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DflIntrst` decimal(19,6) DEFAULT NULL,
  `DfltSlp` decimal(6,0) DEFAULT NULL,
  `DflCrCard` decimal(6,0) DEFAULT NULL,
  `DflBnkCode` char(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DflBnkAcct` char(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DflBranch` char(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UsePaSys` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Serv_Usr` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Serv_Pass` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxIdNum2` char(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxIdNum3` char(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DecSep` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ThousSep` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CurOnRight` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WarnByWhs` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DflBnkAcKy` decimal(6,0) DEFAULT NULL,
  `PriceSys` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DftPVL` decimal(6,0) DEFAULT NULL,
  `useDdctTrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `useDocWrf` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BtchStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrderBatch` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GLMethod` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT 'Item Group',
  `SetSriUniq` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SriUniqFld` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `255History` decimal(6,0) DEFAULT NULL,
  `TaxRateDet` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free37` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StockNoBas` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free39` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CentPmtInc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CentPmtOut` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChCtrAPAct` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChCtrARAct` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free42` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free43` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CaredType` char(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PBSNumber` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PBSGroupNo` char(5) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrgNumber` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActSep` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DspBokpWin` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SHandleWT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SDfltWT` char(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IncresGlAc` char(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PHandleWT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PDfltWT` char(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExWTLiabl` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free44` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AllowPostZ` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PostDiffR` decimal(19,6) DEFAULT NULL,
  `EnableRO` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free48` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free49` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NegAmount` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free61` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `HldCode` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AlphaDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free62` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free63` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free64` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free65` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrderBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RoundMthd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AdrsFromWH` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrderParty` char(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CrtfcateNO` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NINum` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free66` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free67` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CfwAsnMust` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CfwInDflt` decimal(6,0) DEFAULT NULL,
  `CfwOutDflt` decimal(6,0) DEFAULT NULL,
  `free68` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free69` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxRegime` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AliasName` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `DftJPELine` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RdrConfrmd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PorConfrmd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free71` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free72` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChfAcc` decimal(6,0) DEFAULT NULL,
  `TaxMethod` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CEO` decimal(6,0) DEFAULT NULL,
  `free73` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free74` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RndToTDec` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SDfltITWT` char(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PDfltITWT` char(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free75` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free76` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfActCurr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `defTaxVend` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free77` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free78` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free79` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free80` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free89` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoVat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ConsumeMtd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DaysBack` decimal(6,0) DEFAULT NULL,
  `DaysFwrd` decimal(6,0) DEFAULT NULL,
  `IsPAPrn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free82` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCodeCst` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCodeVnd` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `State` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CharMonth` decimal(6,0) DEFAULT NULL,
  `free83` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free84` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free85` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free86` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AltBOEPost` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LDiscTotal` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Code` decimal(6,0) DEFAULT NULL,
  `DfltDunTrm` char(25) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Profession` char(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free88` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfltCDP` decimal(6,0) DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `DflBCACode` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IgrAllCash` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxPayerRf` char(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EmployerRf` char(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PStatAutCh` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PStatDelay` decimal(6,0) DEFAULT NULL,
  `RepBusType` char(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RepBusOthr` char(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BrachNum` char(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BuisnesDsc` char(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReptMethod` char(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctMethod` char(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Bookpitype` char(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActSoftNam` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OpnClsRmrk` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxRndRule` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NegTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ZeroLine` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GBOpenFile` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GBIntface` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfltCDPV` decimal(6,0) DEFAULT NULL,
  `OnHldPert` decimal(19,6) DEFAULT NULL,
  `WTRndRule` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GPPrcntSrv` decimal(19,6) DEFAULT NULL,
  `DspFrznBP` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DspFrznITM` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTAccumAmt` decimal(19,6) DEFAULT NULL,
  `NewDPRCus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ServNature` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickLimit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTAccAmtAR` decimal(19,6) DEFAULT NULL,
  `UseProdPL` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QueryDec` decimal(6,0) DEFAULT NULL,
  `ExRtDefTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `CpyExhRate` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MapService` decimal(6,0) DEFAULT NULL,
  `ODWFreq` decimal(6,0) DEFAULT NULL,
  `UseMltDims` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MDStyle` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTSSep` char(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTSDftChk` decimal(6,0) DEFAULT NULL,
  `GTSDftPye` decimal(6,0) DEFAULT NULL,
  `GTS255Amt` decimal(19,6) DEFAULT NULL,
  `RspOverAmt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DRBlock1` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DRBlock2` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DRBlock3` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DRBlock4` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DRBlock5` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PrjBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SimReport` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SnapShotId` decimal(6,0) DEFAULT NULL,
  `BackOrder` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `HQLocation` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DflWTS` decimal(6,0) DEFAULT NULL,
  `EnbApprDI` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChBPSerie` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChItmSerie` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ETRTaxOffi` decimal(6,0) DEFAULT NULL,
  `ETRTaxPers` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDocExpFrm` decimal(6,0) DEFAULT NULL,
  `PCN874RTyp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BTWDecProv` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BTWDcPrvID` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BTWName` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BTWStreet` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BTWCity` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BTWZip` char(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BTWPhone` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BTWOB` decimal(6,0) DEFAULT NULL,
  `BTWICP` decimal(6,0) DEFAULT NULL,
  `BTWOBFmt` decimal(6,0) DEFAULT NULL,
  `BTWICPFmt` decimal(6,0) DEFAULT NULL,
  `ETRPhoneNo` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDTestMode` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDocGenTyp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDocRptFmt` decimal(6,0) DEFAULT NULL,
  `InputMsg` decimal(6,0) DEFAULT NULL,
  `EDProcess` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PAC` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NotifAlert` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NotifEmail` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free52` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free51` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free50` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free22` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free21` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ETRFaxNo` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ETRMgrPhn` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDFormat` decimal(6,0) DEFAULT NULL,
  `AIDFormat` decimal(6,0) DEFAULT NULL,
  `CrtLineRFQ` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DflJET` char(60) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OnlyPaidIn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PDDEnabled` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `255Days4DD` decimal(6,0) DEFAULT NULL,
  `AutoAddUoM` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoAddPkg` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BinActivat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IssuePriBy` decimal(6,0) DEFAULT NULL,
  `InstFixAst` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeprecCalc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FixAstMod` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NewAcctDe` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ClnZeroPln` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CmdDisBoth` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Cncl255Day` decimal(6,0) DEFAULT NULL,
  `ICDifExPe1` decimal(19,6) DEFAULT NULL,
  `ICDifExPe2` decimal(19,6) DEFAULT NULL,
  `ClsZoDiffR` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ClsNoConfi` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free45` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `free46` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `INVOBPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SplitFBSh` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NotifyRqr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeactivFA` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CshDctFA` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SendAlert` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BdgtPRQDOC` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MBAOnPer` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MBAOnAP` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MBAOnAR` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsReuseNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsReuseNFN` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SIPLReport` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SIPLDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SIPLSeting` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EnbSupplC` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceProcM` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ApyBsActSP` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ApyBsActPV` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ApyBsActPL` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChkQtyINV` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsUpdNstdB` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `logo` longblob,
  `CompID` int NOT NULL AUTO_INCREMENT,
  PRIMARY KEY (`CompID`),
  KEY `DfCustTerm` (`DfCustTerm`),
  KEY `DfVendTerm` (`DfVendTerm`),
  CONSTRAINT `FK_OADM_TO_OCTG_DfVendTeziG7O` FOREIGN KEY (`DfVendTerm`) REFERENCES `OCTG` (`GroupNum`) ON DELETE RESTRICT ON UPDATE RESTRICT,
  CONSTRAINT `OADM_ibfk_1` FOREIGN KEY (`DfCustTerm`) REFERENCES `OCTG` (`GroupNum`) ON DELETE RESTRICT ON UPDATE RESTRICT
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OARG`
--

DROP TABLE IF EXISTS `OARG`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OARG` (
  `CstGrpCode` int NOT NULL AUTO_INCREMENT,
  `CstGrpName` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GroupNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Custom` decimal(19,6) DEFAULT NULL,
  `BuyTax` decimal(19,6) DEFAULT NULL,
  `OtherTax` decimal(19,6) DEFAULT NULL,
  `TotalTax` decimal(19,6) DEFAULT NULL,
  `Locked` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `cstAllcAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `cstExpAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`CstGrpCode`)
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OBIN`
--

DROP TABLE IF EXISTS `OBIN`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OBIN` (
  `AbsEntry` int NOT NULL AUTO_INCREMENT,
  `BinCode` varchar(228) NOT NULL,
  `WhsCode` varchar(8) NOT NULL,
  `SysBin` char(1) DEFAULT 'N',
  `SL1Code` varchar(50) DEFAULT NULL,
  `SL2Code` varchar(50) DEFAULT NULL,
  `SL3Code` varchar(50) DEFAULT NULL,
  `SL4Code` varchar(50) DEFAULT NULL,
  `Attr1Code` varchar(20) DEFAULT NULL,
  `Attr2Code` varchar(20) DEFAULT NULL,
  `Disabled` char(1) DEFAULT 'N',
  `Descr` varchar(50) DEFAULT NULL,
  `BarCode` varchar(100) DEFAULT NULL,
  `MinQty` decimal(19,6) DEFAULT '0.000000',
  `MaxQty` decimal(19,6) DEFAULT '0.000000',
  `ItemWhsCr` char(1) DEFAULT 'N',
  PRIMARY KEY (`AbsEntry`),
  UNIQUE KEY `UK_BinCode` (`BinCode`),
  KEY `IDX_OBIN_WhsCode` (`WhsCode`),
  KEY `IDX_OBIN_Sublevels` (`SL1Code`,`SL2Code`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OCLA`
--

DROP TABLE IF EXISTS `OCLA`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OCLA` (
  `statusID` int NOT NULL AUTO_INCREMENT,
  `name` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `description` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Locked` tinyint(1) NOT NULL DEFAULT '0',
  PRIMARY KEY (`statusID`),
  KEY `name` (`name`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OCPR`
--

DROP TABLE IF EXISTS `OCPR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OCPR` (
  `CntctCode` int NOT NULL AUTO_INCREMENT,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Name` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Position` varchar(90) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Tel1` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Tel2` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Cellolar` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT '0000-000-0000',
  `Fax` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `E_MailL` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT 'n/a',
  `Pager` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Notes1` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Notes2` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `Password` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BirthPlace` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BirthDate` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Gender` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Profession` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `updateDate` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `updateTime` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Title` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BirthCity` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Active` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FirstName` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MiddleName` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LastName` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DestinationLat` decimal(10,8) DEFAULT NULL,
  `DestinationLong` decimal(11,8) DEFAULT NULL,
  PRIMARY KEY (`CntctCode`),
  KEY `CardCode` (`CardCode`)
) ENGINE=InnoDB AUTO_INCREMENT=1624 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OCRD`
--

DROP TABLE IF EXISTS `OCRD`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OCRD` (
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL DEFAULT '',
  `CardName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GroupCode` decimal(6,0) DEFAULT NULL,
  `CmpPrivate` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address` varchar(300) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ZipCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MailAddres` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MailZipCod` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Phone1` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Phone2` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Fax` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CntctPrsn` varchar(90) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Notes` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Balance` decimal(19,6) DEFAULT NULL,
  `ChecksBal` decimal(19,6) DEFAULT NULL,
  `DNotesBal` decimal(19,6) DEFAULT NULL,
  `OrdersBal` decimal(19,6) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `CreditLine` decimal(19,6) DEFAULT NULL,
  `DebtLine` decimal(19,6) DEFAULT NULL,
  `Discount` decimal(19,6) DEFAULT NULL,
  `VatStatus` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DdctStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DdctPrcnt` decimal(19,6) DEFAULT NULL,
  `ValidUntil` date DEFAULT NULL,
  `Chrctrstcs` decimal(6,0) DEFAULT NULL,
  `ExMatchNum` decimal(6,0) DEFAULT NULL,
  `InMatchNum` decimal(6,0) DEFAULT NULL,
  `ListNum` decimal(6,0) DEFAULT NULL,
  `DNoteBalFC` decimal(19,6) DEFAULT NULL,
  `OrderBalFC` decimal(19,6) DEFAULT NULL,
  `DNoteBalSy` decimal(19,6) DEFAULT NULL,
  `OrderBalSy` decimal(19,6) DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BalTrnsfrd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IntrstRate` decimal(19,6) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `CommGrCode` decimal(6,0) DEFAULT NULL,
  `Free_Text` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `PrevYearAc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RateDifAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BalanceSys` decimal(19,6) DEFAULT NULL,
  `BalanceFC` decimal(19,6) DEFAULT NULL,
  `Protected` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Cellular` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AvrageLate` decimal(6,0) DEFAULT NULL,
  `City` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `County` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Country` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MailCity` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MailCounty` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MailCountr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `E_Mail` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Picture` varchar(200) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DflAccount` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DflBranch` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankCode` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AddID` varchar(18) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Pager` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FatherCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardFName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FatherType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup1` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup2` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup3` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup4` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup5` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup6` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup7` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup8` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup9` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup10` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup11` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup12` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup13` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup14` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup15` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup16` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup17` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup18` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup19` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup20` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup21` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup22` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup23` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup24` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup25` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup26` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup27` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup28` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup29` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup30` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup31` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup32` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup33` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup34` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup35` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup36` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup37` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup38` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup39` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup40` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup41` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup42` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup43` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup44` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup45` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup46` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup47` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup48` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup49` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup50` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup51` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup52` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup53` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup54` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup55` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup56` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup57` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup58` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup59` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup60` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup61` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup62` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup63` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup64` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DdctOffice` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `ExportCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DscntObjct` decimal(6,0) DEFAULT NULL,
  `DscntRel` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SPGCounter` decimal(6,0) DEFAULT NULL,
  `SPPCounter` decimal(6,0) DEFAULT NULL,
  `DdctFileNo` varchar(9) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SCNCounter` decimal(6,0) DEFAULT NULL,
  `MinIntrst` decimal(19,6) DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OprCount` decimal(6,0) DEFAULT NULL,
  `ExemptNo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Priority` decimal(6,0) DEFAULT NULL,
  `CreditCard` decimal(6,0) DEFAULT NULL,
  `CrCardNum` varchar(64) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardValid` date DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `LocMth` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `validFor` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `validFrom` date DEFAULT NULL,
  `validTo` date DEFAULT NULL,
  `frozenFor` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `frozenFrom` date DEFAULT NULL,
  `frozenTo` date DEFAULT NULL,
  `sEmployed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MTHCounter` decimal(6,0) DEFAULT NULL,
  `BNKCounter` decimal(6,0) DEFAULT NULL,
  `DdgKey` decimal(6,0) DEFAULT NULL,
  `DdtKey` decimal(6,0) DEFAULT NULL,
  `ValidComm` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrozenComm` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `chainStore` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DiscInRet` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `State1` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `State2` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipType` decimal(6,0) DEFAULT NULL,
  `DebPayAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDef` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Block` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MailBlock` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Password` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ECVatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Deleted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IBAN` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocEntry` decimal(6,0) DEFAULT NULL,
  `FormCode` decimal(6,0) DEFAULT NULL,
  `Box1099` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PymCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrder` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PartDelivr` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `DunnDate` date DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankCountr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CollecAuth` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DME` varchar(5) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `InstrucKey` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SinglePaym` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ISRBillId` varchar(9) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PaymBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RefDetails` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `HouseBank` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerIdNum` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PyBlckDesc` decimal(6,0) DEFAULT NULL,
  `HousBnkCry` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `HousBnkAct` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `HousBnkBrn` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ProjectCod` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SysMatchNo` decimal(6,0) DEFAULT NULL,
  `VatIdUnCmp` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AgentCode` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TolrncDays` decimal(6,0) DEFAULT NULL,
  `SelfInvoic` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LetterNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `250Amount` decimal(19,6) DEFAULT NULL,
  `FromDate` date DEFAULT NULL,
  `ToDate` date DEFAULT NULL,
  `WTLiable` tinyint(1) DEFAULT '0',
  `CrtfcateNO` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpireDate` date DEFAULT NULL,
  `NINum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AccCritria` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTCode` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Equ` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `HldCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ConnBP` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MltMthNum` decimal(6,0) DEFAULT NULL,
  `TypWTReprt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VATRegNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RepName` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Industry` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Business` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTTaxCat` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsDomestic` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsResident` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoCalBCG` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OtrCtlAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AliasName` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Building` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MailBuildi` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BoEPrsnt` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BoEDiscnt` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BoEOnClct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UnpaidBoE` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ITWTCode` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DunTerm` varchar(25) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChannlBP` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfTcnician` decimal(6,0) DEFAULT NULL,
  `Territory` decimal(6,0) DEFAULT NULL,
  `BillToDef` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmClear` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IntrntSite` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `HousActKey` decimal(6,0) DEFAULT NULL,
  `Profession` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CDPNum` decimal(6,0) DEFAULT NULL,
  `DflBankKey` decimal(6,0) DEFAULT NULL,
  `BCACode` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RegNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VerifNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankCtlKey` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `HousCtlKey` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AddrType` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `InsurOp347` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MailAddrTy` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StreetNo` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MailStrNo` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxRndRule` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VendTID` decimal(6,0) DEFAULT NULL,
  `ThreshOver` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SurOver` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VendorOcup` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OpCode347` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmIntAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `PlngGroup` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatIDNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Affiliate` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MivzExpSts` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `HierchDdct` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CertWHT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CertBKeep` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WHShaamGrp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IndustryC` decimal(6,0) DEFAULT NULL,
  `DatevAcct` decimal(6,0) DEFAULT NULL,
  `DatevFirst` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTSRegNum` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTSBankAct` varchar(80) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTSBilAddr` varchar(80) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `HsBnkSwift` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `HsBnkIBAN` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DflSwift` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoPost` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IntrAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FeeAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CpnNo` decimal(6,0) DEFAULT NULL,
  `NTSWebSite` decimal(6,0) DEFAULT NULL,
  `DflIBAN` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `Number` decimal(6,0) DEFAULT NULL,
  `EDocExpFrm` decimal(6,0) DEFAULT NULL,
  `TaxIdIdent` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Attachment` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AtcEntry` decimal(6,0) DEFAULT NULL,
  `latitude` decimal(10,7) DEFAULT NULL,
  `longitude` decimal(10,7) DEFAULT NULL,
  PRIMARY KEY (`CardCode`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OCRG`
--

DROP TABLE IF EXISTS `OCRG`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OCRG` (
  `GroupCode` decimal(6,0) NOT NULL DEFAULT '0',
  `GroupName` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GroupType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Locked` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  PRIMARY KEY (`GroupCode`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OCRN`
--

DROP TABLE IF EXISTS `OCRN`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OCRN` (
  `CurrCode` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CurrName` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChkName` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Chk100Name` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocCurrCod` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrgnName` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `F100Name` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Locked` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `RoundSys` decimal(6,0) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `Decimals` decimal(6,0) DEFAULT NULL,
  `ISRCalc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RoundPym` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ConvUnit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCurr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Factor` decimal(19,6) DEFAULT NULL,
  `ChkNamePl` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Chk100NPl` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrgnNamePl` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `F100NamePl` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ISOCurrCod` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MaxInDiff` decimal(19,6) DEFAULT NULL,
  `MaxOutDiff` decimal(19,6) DEFAULT NULL,
  `MaxInPcnt` decimal(19,6) DEFAULT NULL,
  `MaxOutPcnt` decimal(19,6) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OCTG`
--

DROP TABLE IF EXISTS `OCTG`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OCTG` (
  `GroupNum` int NOT NULL AUTO_INCREMENT,
  `PymntGroup` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayDuMonth` varchar(12) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExtraMonth` decimal(6,0) DEFAULT NULL,
  `ExtraDays` decimal(6,0) DEFAULT NULL,
  `PaymntsNum` decimal(6,0) DEFAULT NULL,
  `CredLimit` decimal(19,6) DEFAULT NULL,
  `VolumDscnt` decimal(19,6) DEFAULT NULL,
  `LatePyChrg` decimal(19,6) DEFAULT NULL,
  `ObligLimit` decimal(19,6) DEFAULT NULL,
  `ListNum` decimal(6,0) DEFAULT NULL,
  `Payments` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumOfPmnts` decimal(6,0) DEFAULT NULL,
  `Payment1` decimal(19,6) DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `OpenRcpt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DiscCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DunningCod` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BslineDate` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `InstNum` decimal(6,0) DEFAULT NULL,
  `TolDays` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CrdMthd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`GroupNum`)
) ENGINE=InnoDB AUTO_INCREMENT=43 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OCTR`
--

DROP TABLE IF EXISTS `OCTR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OCTR` (
  `ContractID` int NOT NULL AUTO_INCREMENT COMMENT 'Contract No.',
  `CstmrCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL COMMENT 'Customer Code',
  `CstmrName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Customer Name',
  `CntctCode` int DEFAULT NULL COMMENT 'Contact Person Code',
  `Owner` int DEFAULT NULL COMMENT 'Owner / Employee ID',
  `Status` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'A' COMMENT 'Contract Status (e.g., A=Approved, T=Terminated)',
  `CntrcTmplt` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Contract Template',
  `CntrcType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Contract Type (e.g., R=Regular, W=Warranty, S=Serial)',
  `Renewal` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'N' COMMENT 'Renewal Flag (Y/N)',
  `RemindVal` int DEFAULT NULL COMMENT 'Reminder Time Value',
  `RemindUnit` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Remind Unit (D=Days, W=Weeks, M=Months)',
  `Duration` int DEFAULT NULL COMMENT 'Duration of Coverage',
  `StartDate` date DEFAULT NULL COMMENT 'Start Date',
  `EndDate` date DEFAULT NULL COMMENT 'End Date',
  `ResponsVal` int DEFAULT NULL COMMENT 'Resolution Time Value',
  `ResponsUnt` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Resolution Unit',
  `Descriptio` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Description',
  `SrcDocType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Source Document Type',
  `DocNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Source Document No.',
  `MonEnabled` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Y' COMMENT 'Monday Enabled (Y/N)',
  `TueEnabled` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Y' COMMENT 'Tuesday Enabled (Y/N)',
  `WedEnabled` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Y' COMMENT 'Wednesday Enabled (Y/N)',
  `ThuEnabled` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Y' COMMENT 'Thursday Enabled (Y/N)',
  `FriEnabled` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Y' COMMENT 'Friday Enabled (Y/N)',
  `SatEnabled` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'N' COMMENT 'Saturday Enabled (Y/N)',
  `SunEnabled` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'N' COMMENT 'Sunday Enabled (Y/N)',
  `MonStart` time DEFAULT NULL COMMENT 'Monday Start Time',
  `MonEnd` time DEFAULT NULL COMMENT 'Monday End Time',
  `TueStart` time DEFAULT NULL COMMENT 'Tuesday Start Time',
  `TueEnd` time DEFAULT NULL COMMENT 'Tuesday End Time',
  `WedStart` time DEFAULT NULL COMMENT 'Wednesday Start Time',
  `WedEnd` time DEFAULT NULL COMMENT 'Wednesday End Time',
  `ThuStart` time DEFAULT NULL COMMENT 'Thursday Start Time',
  `ThuEnd` time DEFAULT NULL COMMENT 'Thursday End Time',
  `FriStart` time DEFAULT NULL COMMENT 'Friday Start Time',
  `FriEnd` time DEFAULT NULL COMMENT 'Friday End Time',
  `SatStart` time DEFAULT NULL COMMENT 'Saturday Start Time',
  `SatEnd` time DEFAULT NULL COMMENT 'Saturday End Time',
  `SunStrart` time DEFAULT NULL COMMENT 'Sunday Start Time',
  `SunEnd` time DEFAULT NULL COMMENT 'Sunday End Time',
  `InclParts` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'N' COMMENT 'Include Parts (Y/N)',
  `InclWork` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'N' COMMENT 'Include Labor (Y/N)',
  `InclTravel` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'N' COMMENT 'Include Travel (Y/N)',
  `Attachment` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci COMMENT 'Attachments Data Field',
  `CreateDate` date DEFAULT NULL COMMENT 'Creation Date',
  `Remarks1` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci COMMENT 'Template Remarks',
  `Remarks2` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci COMMENT 'Remarks',
  `RemindFlg` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'N' COMMENT 'Reminder Sent (Y/N)',
  `CTR1Count` int DEFAULT '0' COMMENT 'CTR1 Line Counter',
  `DocEntry` int DEFAULT NULL COMMENT 'Linked Document No.',
  `RemTmDays` int DEFAULT NULL COMMENT 'Remind Time in Days',
  `ResTmHours` decimal(10,2) DEFAULT NULL COMMENT 'Response Time in Hours',
  `InclHldays` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'N' COMMENT 'Include Holidays (Y/N)',
  `SrvcType` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Service Type',
  `TermDate` date DEFAULT NULL COMMENT 'Termination Date',
  `ResponseV` int DEFAULT NULL COMMENT 'Response Time Value',
  `ResponseU` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Response Unit',
  `AtcEntry` int DEFAULT NULL COMMENT 'Attachment Entry Key',
  `Transfered` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Year Transfer Status Code',
  `Instance` int DEFAULT NULL COMMENT 'Instance Version Index ID',
  PRIMARY KEY (`ContractID`),
  KEY `IDX_OCTR_Customer` (`CstmrCode`)
) ENGINE=InnoDB AUTO_INCREMENT=7 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `ODLN`
--

DROP TABLE IF EXISTS `ODLN`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `ODLN` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Printed` tinyint(1) NOT NULL DEFAULT '0',
  `DocStatus` tinyint(1) NOT NULL DEFAULT '0',
  `InvntSttus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `DocDueDate` date DEFAULT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `DiscSum` decimal(19,6) DEFAULT NULL,
  `DiscSumFC` decimal(19,6) DEFAULT NULL,
  `DocCur` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `PaidToDate` decimal(19,6) DEFAULT NULL,
  `PaidFC` decimal(19,6) DEFAULT NULL,
  `GrosProfit` decimal(19,6) DEFAULT NULL,
  `GrosProfFC` decimal(19,6) DEFAULT NULL,
  `Ref1` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Ref2` varchar(11) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Comments` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DRno` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `ReceiptNum` decimal(6,0) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `TrnspCode` decimal(6,0) DEFAULT NULL,
  `PartSupply` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Confirmed` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `ImportEnt` decimal(6,0) DEFAULT NULL,
  `CreateTran` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SummryType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `UpdInvnt` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `UpdCardBal` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `InvntDirec` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `ShowSCN` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FatherCard` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `CurSource` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `DiscSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `PaidSys` decimal(19,6) DEFAULT NULL,
  `FatherType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GrosProfSy` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `IsICT` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `Filler` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StampNum` varchar(16) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `isCrin` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `selfInv` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatPaid` decimal(19,6) DEFAULT NULL,
  `VatPaidFC` decimal(19,6) DEFAULT NULL,
  `VatPaidSys` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `WddStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `draftKey` decimal(6,0) DEFAULT NULL,
  `TotalExpns` decimal(19,6) DEFAULT NULL,
  `TotalExpFC` decimal(19,6) DEFAULT NULL,
  `TotalExpSC` decimal(19,6) DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `Address2` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `Exported` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StationID` decimal(6,0) DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NetProc` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AqcsTax` decimal(19,6) DEFAULT NULL,
  `AqcsTaxFC` decimal(19,6) DEFAULT NULL,
  `AqcsTaxSC` decimal(19,6) DEFAULT NULL,
  `CashDiscPr` decimal(19,6) DEFAULT NULL,
  `CashDiscnt` decimal(19,6) DEFAULT NULL,
  `CashDiscFC` decimal(19,6) DEFAULT NULL,
  `CashDiscSC` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PaymentRef` varchar(27) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `RoundDif` decimal(19,6) DEFAULT NULL,
  `RoundDifFC` decimal(19,6) DEFAULT NULL,
  `RoundDifSy` decimal(19,6) DEFAULT NULL,
  `CheckDigit` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Form1099` decimal(6,0) DEFAULT NULL,
  `Box1099` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `submitted` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PoPrss` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Rounding` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RevisionPo` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Segment` decimal(6,0) DEFAULT NULL,
  `ReqDate` date DEFAULT NULL,
  `CancelDate` date DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Pick` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PeyMethod` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PayBlock` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `MaxDscn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Reserve` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Max1099` decimal(19,6) DEFAULT NULL,
  `CntrlBnk` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PickRmrk` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ISRCodLine` varchar(53) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ExpAppl` decimal(19,6) DEFAULT NULL,
  `ExpApplFC` decimal(19,6) DEFAULT NULL,
  `ExpApplSC` decimal(19,6) DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LetterNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FromDate` date DEFAULT NULL,
  `ToDate` date DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BoeReserev` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AgentCode` varchar(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `Installmnt` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NnSbAmnt` decimal(19,6) DEFAULT NULL,
  `NnSbAmntSC` decimal(19,6) DEFAULT NULL,
  `NbSbAmntFC` decimal(19,6) DEFAULT NULL,
  `ExepAmnt` decimal(19,6) DEFAULT NULL,
  `ExepAmntSC` decimal(19,6) DEFAULT NULL,
  `ExepAmntFC` decimal(19,6) DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `CorrExt` varchar(25) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CorrInv` decimal(6,0) DEFAULT NULL,
  `NCorrInv` decimal(6,0) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `CtlAccount` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VATRegNum` varchar(12) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TxInvRptNo` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TxInvRptDt` date DEFAULT NULL,
  `KVVATCode` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WTDetails` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SumAbsId` decimal(6,0) DEFAULT NULL,
  `SumRptDate` date DEFAULT NULL,
  `PIndicator` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ManualNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `NnSbVAt` decimal(19,6) DEFAULT NULL,
  `NnSbVAtSC` decimal(19,6) DEFAULT NULL,
  `NbSbVAtFC` decimal(19,6) DEFAULT NULL,
  `ExptVAt` decimal(19,6) DEFAULT NULL,
  `ExptVAtSC` decimal(19,6) DEFAULT NULL,
  `ExptVAtFC` decimal(19,6) DEFAULT NULL,
  `LYPmtAt` decimal(19,6) DEFAULT NULL,
  `LYPmtAtSC` decimal(19,6) DEFAULT NULL,
  `LYPmtAtFC` decimal(19,6) DEFAULT NULL,
  `ExpAnSum` decimal(19,6) DEFAULT NULL,
  `ExpAnSys` decimal(19,6) DEFAULT NULL,
  `ExpAnFrgn` decimal(19,6) DEFAULT NULL,
  `DocSubType` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DpmStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DpmAmnt` decimal(19,6) DEFAULT NULL,
  `DpmAmntSC` decimal(19,6) DEFAULT NULL,
  `DpmAmntFC` decimal(19,6) DEFAULT NULL,
  `DpmDrawn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DpmPrcnt` decimal(19,6) DEFAULT NULL,
  `PaidSum` decimal(19,6) DEFAULT NULL,
  `PaidSumFc` decimal(19,6) DEFAULT NULL,
  `PaidSumSc` decimal(19,6) DEFAULT NULL,
  `FolioPref` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `DpmAppl` decimal(19,6) DEFAULT NULL,
  `DpmApplFc` decimal(19,6) DEFAULT NULL,
  `DpmApplSc` decimal(19,6) DEFAULT NULL,
  `LPgFolioN` decimal(6,0) DEFAULT NULL,
  `Header` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Footer` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Posted` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `BPChCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BPChCntc` decimal(6,0) DEFAULT NULL,
  `PayToCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IsPaytoBnk` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BnkCntry` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BankCode` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BnkAccount` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BnkBranch` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `isIns` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TrackNo` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VersionNum` varchar(11) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `BPNameOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BillToOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ShipToOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RetInvoice` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `MInvNum` decimal(6,0) DEFAULT NULL,
  `MInvDate` date DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SubStr` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Model` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TaxOnExp` decimal(19,6) DEFAULT NULL,
  `TaxOnExpFc` decimal(19,6) DEFAULT NULL,
  `TaxOnExpSc` decimal(19,6) DEFAULT NULL,
  `TaxOnExAp` decimal(19,6) DEFAULT NULL,
  `TaxOnExApF` decimal(19,6) DEFAULT NULL,
  `TaxOnExApS` decimal(19,6) DEFAULT NULL,
  `LastPmnTyp` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LndCstNum` decimal(6,0) DEFAULT NULL,
  `UseCorrVat` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BlkCredMmo` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OpenForLaC` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Excised` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ExcRefDate` date DEFAULT NULL,
  `ExcRmvTime` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SrvGpPrcnt` decimal(19,6) DEFAULT NULL,
  `DepositNum` decimal(6,0) DEFAULT NULL,
  `CertNum` varchar(31) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DutyStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AutoCrtFlw` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FlwRefDate` date DEFAULT NULL,
  `FlwRefNum` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatJENum` decimal(6,0) DEFAULT NULL,
  `DpmVat` decimal(19,6) DEFAULT NULL,
  `DpmVatFc` decimal(19,6) DEFAULT NULL,
  `DpmVatSc` decimal(19,6) DEFAULT NULL,
  `DpmAppVat` decimal(19,6) DEFAULT NULL,
  `DpmAppVatF` decimal(19,6) DEFAULT NULL,
  `DpmAppVatS` decimal(19,6) DEFAULT NULL,
  `InsurOp347` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IgnRelDoc` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BuildDesc` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Checker` decimal(6,0) DEFAULT NULL,
  `Payee` decimal(6,0) DEFAULT NULL,
  `CopyNumber` decimal(6,0) DEFAULT NULL,
  `SSIExmpt` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PQTGrpSer` decimal(6,0) DEFAULT NULL,
  `PQTGrpNum` decimal(6,0) DEFAULT NULL,
  `PQTGrpHW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ReopOriDoc` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ReopManCls` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocManClsd` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`),
  UNIQUE KEY `DocNum_UNIQUE` (`DocNum`)
) ENGINE=InnoDB AUTO_INCREMENT=1088 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `ODLN2`
--

DROP TABLE IF EXISTS `ODLN2`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `ODLN2` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `DocType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Printed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT 'N',
  `DocStatus` tinyint(1) NOT NULL DEFAULT '0',
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `DocDueDate` date DEFAULT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `DiscSum` decimal(19,6) DEFAULT NULL,
  `DiscSumFC` decimal(19,6) DEFAULT NULL,
  `DocCur` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `PaidToDate` decimal(19,6) DEFAULT NULL,
  `PaidFC` decimal(19,6) DEFAULT NULL,
  `GrosProfit` decimal(19,6) DEFAULT NULL,
  `GrosProfFC` decimal(19,6) DEFAULT NULL,
  `Ref1` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref2` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Comments` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DRno` int NOT NULL,
  `ReceiptNum` decimal(6,0) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `TrnspCode` decimal(6,0) DEFAULT NULL,
  `PartSupply` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Confirmed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `ImportEnt` decimal(6,0) DEFAULT NULL,
  `CreateTran` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SummryType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdInvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdCardBal` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `InvntDirec` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `ShowSCN` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FatherCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `CurSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `DiscSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `PaidSys` decimal(19,6) DEFAULT NULL,
  `FatherType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrosProfSy` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `IsICT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `Filler` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StampNum` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isCrin` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `selfInv` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPaid` decimal(19,6) DEFAULT NULL,
  `VatPaidFC` decimal(19,6) DEFAULT NULL,
  `VatPaidSys` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `WddStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `draftKey` decimal(6,0) DEFAULT NULL,
  `TotalExpns` decimal(19,6) DEFAULT NULL,
  `TotalExpFC` decimal(19,6) DEFAULT NULL,
  `TotalExpSC` decimal(19,6) DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `Address2` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `Exported` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StationID` decimal(6,0) DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NetProc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AqcsTax` decimal(19,6) DEFAULT NULL,
  `AqcsTaxFC` decimal(19,6) DEFAULT NULL,
  `AqcsTaxSC` decimal(19,6) DEFAULT NULL,
  `CashDiscPr` decimal(19,6) DEFAULT NULL,
  `CashDiscnt` decimal(19,6) DEFAULT NULL,
  `CashDiscFC` decimal(19,6) DEFAULT NULL,
  `CashDiscSC` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PaymentRef` varchar(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `RoundDif` decimal(19,6) DEFAULT NULL,
  `RoundDifFC` decimal(19,6) DEFAULT NULL,
  `RoundDifSy` decimal(19,6) DEFAULT NULL,
  `CheckDigit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Form1099` decimal(6,0) DEFAULT NULL,
  `Box1099` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `submitted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoPrss` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rounding` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevisionPo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Segment` decimal(6,0) DEFAULT NULL,
  `ReqDate` date DEFAULT NULL,
  `CancelDate` date DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Pick` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PeyMethod` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `MaxDscn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Reserve` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Max1099` decimal(19,6) DEFAULT NULL,
  `CntrlBnk` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickRmrk` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ISRCodLine` varchar(53) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpAppl` decimal(19,6) DEFAULT NULL,
  `ExpApplFC` decimal(19,6) DEFAULT NULL,
  `ExpApplSC` decimal(19,6) DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LetterNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FromDate` date DEFAULT NULL,
  `ToDate` date DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BoeReserev` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AgentCode` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `Installmnt` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NnSbAmnt` decimal(19,6) DEFAULT NULL,
  `NnSbAmntSC` decimal(19,6) DEFAULT NULL,
  `NbSbAmntFC` decimal(19,6) DEFAULT NULL,
  `ExepAmnt` decimal(19,6) DEFAULT NULL,
  `ExepAmntSC` decimal(19,6) DEFAULT NULL,
  `ExepAmntFC` decimal(19,6) DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `CorrExt` varchar(25) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CorrInv` decimal(6,0) DEFAULT NULL,
  `NCorrInv` decimal(6,0) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `CtlAccount` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VATRegNum` varchar(12) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptDt` date DEFAULT NULL,
  `KVVATCode` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTDetails` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SumAbsId` decimal(6,0) DEFAULT NULL,
  `SumRptDate` date DEFAULT NULL,
  `PIndicator` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ManualNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `NnSbVAt` decimal(19,6) DEFAULT NULL,
  `NnSbVAtSC` decimal(19,6) DEFAULT NULL,
  `NbSbVAtFC` decimal(19,6) DEFAULT NULL,
  `ExptVAt` decimal(19,6) DEFAULT NULL,
  `ExptVAtSC` decimal(19,6) DEFAULT NULL,
  `ExptVAtFC` decimal(19,6) DEFAULT NULL,
  `LYPmtAt` decimal(19,6) DEFAULT NULL,
  `LYPmtAtSC` decimal(19,6) DEFAULT NULL,
  `LYPmtAtFC` decimal(19,6) DEFAULT NULL,
  `ExpAnSum` decimal(19,6) DEFAULT NULL,
  `ExpAnSys` decimal(19,6) DEFAULT NULL,
  `ExpAnFrgn` decimal(19,6) DEFAULT NULL,
  `DocSubType` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmAmnt` decimal(19,6) DEFAULT NULL,
  `DpmAmntSC` decimal(19,6) DEFAULT NULL,
  `DpmAmntFC` decimal(19,6) DEFAULT NULL,
  `DpmDrawn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmPrcnt` decimal(19,6) DEFAULT NULL,
  `PaidSum` decimal(19,6) DEFAULT NULL,
  `PaidSumFc` decimal(19,6) DEFAULT NULL,
  `PaidSumSc` decimal(19,6) DEFAULT NULL,
  `FolioPref` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `DpmAppl` decimal(19,6) DEFAULT NULL,
  `DpmApplFc` decimal(19,6) DEFAULT NULL,
  `DpmApplSc` decimal(19,6) DEFAULT NULL,
  `LPgFolioN` decimal(6,0) DEFAULT NULL,
  `Header` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Footer` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Posted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `BPChCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPChCntc` decimal(6,0) DEFAULT NULL,
  `PayToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsPaytoBnk` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkCntry` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankCode` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkAccount` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkBranch` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isIns` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TrackNo` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VersionNum` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `BPNameOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BillToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RetInvoice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `MInvNum` decimal(6,0) DEFAULT NULL,
  `MInvDate` date DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Model` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxOnExp` decimal(19,6) DEFAULT NULL,
  `TaxOnExpFc` decimal(19,6) DEFAULT NULL,
  `TaxOnExpSc` decimal(19,6) DEFAULT NULL,
  `TaxOnExAp` decimal(19,6) DEFAULT NULL,
  `TaxOnExApF` decimal(19,6) DEFAULT NULL,
  `TaxOnExApS` decimal(19,6) DEFAULT NULL,
  `LastPmnTyp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LndCstNum` decimal(6,0) DEFAULT NULL,
  `UseCorrVat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlkCredMmo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OpenForLaC` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExcRefDate` date DEFAULT NULL,
  `ExcRmvTime` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SrvGpPrcnt` decimal(19,6) DEFAULT NULL,
  `DepositNum` decimal(6,0) DEFAULT NULL,
  `CertNum` varchar(31) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DutyStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoCrtFlw` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FlwRefDate` date DEFAULT NULL,
  `FlwRefNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatJENum` decimal(6,0) DEFAULT NULL,
  `DpmVat` decimal(19,6) DEFAULT NULL,
  `DpmVatFc` decimal(19,6) DEFAULT NULL,
  `DpmVatSc` decimal(19,6) DEFAULT NULL,
  `DpmAppVat` decimal(19,6) DEFAULT NULL,
  `DpmAppVatF` decimal(19,6) DEFAULT NULL,
  `DpmAppVatS` decimal(19,6) DEFAULT NULL,
  `InsurOp347` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IgnRelDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BuildDesc` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Checker` decimal(6,0) DEFAULT NULL,
  `Payee` decimal(6,0) DEFAULT NULL,
  `CopyNumber` decimal(6,0) DEFAULT NULL,
  `SSIExmpt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTGrpSer` decimal(6,0) DEFAULT NULL,
  `PQTGrpNum` decimal(6,0) DEFAULT NULL,
  `PQTGrpHW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopOriDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopManCls` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `ODRF`
--

DROP TABLE IF EXISTS `ODRF`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `ODRF` (
  `DocEntry` decimal(6,0) DEFAULT NULL,
  `DocNum` decimal(6,0) DEFAULT NULL,
  `DocType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Printed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DocStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DocDate` date NOT NULL,
  `DocDueDate` date NOT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `DiscSum` decimal(19,6) DEFAULT NULL,
  `DiscSumFC` decimal(19,6) DEFAULT NULL,
  `DocCur` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `PaidToDate` decimal(19,6) DEFAULT NULL,
  `PaidFC` decimal(19,6) DEFAULT NULL,
  `GrosProfit` decimal(19,6) DEFAULT NULL,
  `GrosProfFC` decimal(19,6) DEFAULT NULL,
  `Ref1` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Ref2` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Comments` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `TransId` decimal(6,0) DEFAULT NULL,
  `ReceiptNum` decimal(6,0) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `TrnspCode` decimal(6,0) DEFAULT NULL,
  `PartSupply` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Confirmed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `ImportEnt` decimal(6,0) DEFAULT NULL,
  `CreateTran` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `SummryType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `UpdInvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `UpdCardBal` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `InvntDirec` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `ShowSCN` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `FatherCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `CurSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `DiscSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `PaidSys` decimal(19,6) DEFAULT NULL,
  `FatherType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `GrosProfSy` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date NOT NULL,
  `IsICT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `CreateDate` date NOT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `TaxDate` date NOT NULL,
  `Filler` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `StampNum` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `isCrin` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `selfInv` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `VatPaid` decimal(19,6) DEFAULT NULL,
  `VatPaidFC` decimal(19,6) DEFAULT NULL,
  `VatPaidSys` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `WddStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `draftKey` decimal(6,0) DEFAULT NULL,
  `TotalExpns` decimal(19,6) DEFAULT NULL,
  `TotalExpFC` decimal(19,6) DEFAULT NULL,
  `TotalExpSC` decimal(19,6) DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `Address2` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `Exported` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `StationID` decimal(6,0) DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `NetProc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `AqcsTax` decimal(19,6) DEFAULT NULL,
  `AqcsTaxFC` decimal(19,6) DEFAULT NULL,
  `AqcsTaxSC` decimal(19,6) DEFAULT NULL,
  `CashDiscPr` decimal(19,6) DEFAULT NULL,
  `CashDiscnt` decimal(19,6) DEFAULT NULL,
  `CashDiscFC` decimal(19,6) DEFAULT NULL,
  `CashDiscSC` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PaymentRef` varchar(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `RoundDif` decimal(19,6) DEFAULT NULL,
  `RoundDifFC` decimal(19,6) DEFAULT NULL,
  `RoundDifSy` decimal(19,6) DEFAULT NULL,
  `CheckDigit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Form1099` decimal(6,0) DEFAULT NULL,
  `Box1099` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `submitted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PoPrss` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Rounding` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `RevisionPo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Segment` decimal(6,0) DEFAULT NULL,
  `ReqDate` date NOT NULL,
  `CancelDate` date NOT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Pick` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PeyMethod` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PayBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `MaxDscn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Reserve` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Max1099` decimal(19,6) DEFAULT NULL,
  `CntrlBnk` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PickRmrk` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ISRCodLine` varchar(53) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ExpAppl` decimal(19,6) DEFAULT NULL,
  `ExpApplFC` decimal(19,6) DEFAULT NULL,
  `ExpApplSC` decimal(19,6) DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `LetterNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `FromDate` date NOT NULL,
  `ToDate` date NOT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BoeReserev` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `AgentCode` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `Installmnt` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `NnSbAmnt` decimal(19,6) DEFAULT NULL,
  `NnSbAmntSC` decimal(19,6) DEFAULT NULL,
  `NbSbAmntFC` decimal(19,6) DEFAULT NULL,
  `ExepAmnt` decimal(19,6) DEFAULT NULL,
  `ExepAmntSC` decimal(19,6) DEFAULT NULL,
  `ExepAmntFC` decimal(19,6) DEFAULT NULL,
  `VatDate` date NOT NULL,
  `CorrExt` varchar(25) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `CorrInv` decimal(6,0) DEFAULT NULL,
  `NCorrInv` decimal(6,0) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `CtlAccount` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `VATRegNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `TxInvRptNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `TxInvRptDt` date NOT NULL,
  `KVVATCode` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `WTDetails` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `SumAbsId` decimal(6,0) DEFAULT NULL,
  `SumRptDate` date NOT NULL,
  `PIndicator` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ManualNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `NnSbVAt` decimal(19,6) DEFAULT NULL,
  `NnSbVAtSC` decimal(19,6) DEFAULT NULL,
  `NbSbVAtFC` decimal(19,6) DEFAULT NULL,
  `ExptVAt` decimal(19,6) DEFAULT NULL,
  `ExptVAtSC` decimal(19,6) DEFAULT NULL,
  `ExptVAtFC` decimal(19,6) DEFAULT NULL,
  `LYPmtAt` decimal(19,6) DEFAULT NULL,
  `LYPmtAtSC` decimal(19,6) DEFAULT NULL,
  `LYPmtAtFC` decimal(19,6) DEFAULT NULL,
  `ExpAnSum` decimal(19,6) DEFAULT NULL,
  `ExpAnSys` decimal(19,6) DEFAULT NULL,
  `ExpAnFrgn` decimal(19,6) DEFAULT NULL,
  `DocSubType` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DpmStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DpmAmnt` decimal(19,6) DEFAULT NULL,
  `DpmAmntSC` decimal(19,6) DEFAULT NULL,
  `DpmAmntFC` decimal(19,6) DEFAULT NULL,
  `DpmDrawn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DpmPrcnt` decimal(19,6) DEFAULT NULL,
  `PaidSum` decimal(19,6) DEFAULT NULL,
  `PaidSumFc` decimal(19,6) DEFAULT NULL,
  `PaidSumSc` decimal(19,6) DEFAULT NULL,
  `FolioPref` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `DpmAppl` decimal(19,6) DEFAULT NULL,
  `DpmApplFc` decimal(19,6) DEFAULT NULL,
  `DpmApplSc` decimal(19,6) DEFAULT NULL,
  `LPgFolioN` decimal(6,0) DEFAULT NULL,
  `Header` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `Footer` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `Posted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `BPChCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BPChCntc` decimal(6,0) DEFAULT NULL,
  `PayToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `IsPaytoBnk` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BnkCntry` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BankCode` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BnkAccount` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BnkBranch` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `isIns` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `TrackNo` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `VersionNum` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `BPNameOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BillToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ShipToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `RetInvoice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ClsDate` date NOT NULL,
  `MInvNum` decimal(6,0) DEFAULT NULL,
  `MInvDate` date NOT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `SubStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Model` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `TaxOnExp` decimal(19,6) DEFAULT NULL,
  `TaxOnExpFc` decimal(19,6) DEFAULT NULL,
  `TaxOnExpSc` decimal(19,6) DEFAULT NULL,
  `TaxOnExAp` decimal(19,6) DEFAULT NULL,
  `TaxOnExApF` decimal(19,6) DEFAULT NULL,
  `TaxOnExApS` decimal(19,6) DEFAULT NULL,
  `LastPmnTyp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `LndCstNum` decimal(6,0) DEFAULT NULL,
  `UseCorrVat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BlkCredMmo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `OpenForLaC` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Excised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ExcRefDate` date NOT NULL,
  `ExcRmvTime` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `SrvGpPrcnt` decimal(19,6) DEFAULT NULL,
  `DepositNum` decimal(6,0) DEFAULT NULL,
  `CertNum` varchar(31) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DutyStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `AutoCrtFlw` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `FlwRefDate` date NOT NULL,
  `FlwRefNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `VatJENum` decimal(6,0) DEFAULT NULL,
  `DpmVat` decimal(19,6) DEFAULT NULL,
  `DpmVatFc` decimal(19,6) DEFAULT NULL,
  `DpmVatSc` decimal(19,6) DEFAULT NULL,
  `DpmAppVat` decimal(19,6) DEFAULT NULL,
  `DpmAppVatF` decimal(19,6) DEFAULT NULL,
  `DpmAppVatS` decimal(19,6) DEFAULT NULL,
  `InsurOp347` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `IgnRelDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BuildDesc` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Checker` decimal(6,0) DEFAULT NULL,
  `Payee` decimal(6,0) DEFAULT NULL,
  `CopyNumber` decimal(6,0) DEFAULT NULL,
  `SSIExmpt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PQTGrpSer` decimal(6,0) DEFAULT NULL,
  `PQTGrpNum` decimal(6,0) DEFAULT NULL,
  `PQTGrpHW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ReopOriDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ReopManCls` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DocManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ClosingOpt` decimal(6,0) DEFAULT NULL,
  `SpecDate` date NOT NULL,
  `Ordered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `NTSApprov` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `NTSWebSite` decimal(6,0) DEFAULT NULL,
  `NTSeTaxNo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `NTSApprNo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PayDuMonth` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ExtraMonth` decimal(6,0) DEFAULT NULL,
  `ExtraDays` decimal(6,0) DEFAULT NULL,
  `CdcOffset` decimal(6,0) DEFAULT NULL,
  `SignMsg` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `SignDigest` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `CertifNum` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `KeyVersion` decimal(6,0) DEFAULT NULL,
  `EDocGenTyp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ESeries` decimal(6,0) DEFAULT NULL,
  `EDocNum` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `EDocExpFrm` decimal(6,0) DEFAULT NULL,
  `OnlineQuo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `POSEqNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `POSManufSN` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `POSCashN` decimal(6,0) DEFAULT NULL,
  `EDocStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `EDocCntnt` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `EDocProces` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `EDocErrCod` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `EDocErrMsg` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `EDocCancel` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `EDocTest` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `EDocPrefix` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `CUP` decimal(6,0) DEFAULT NULL,
  `CIG` decimal(6,0) DEFAULT NULL,
  `DpmAsDscnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Attachment` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `AtcEntry` decimal(6,0) DEFAULT NULL,
  `SupplCode` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `GTSRlvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OFPR`
--

DROP TABLE IF EXISTS `OFPR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OFPR` (
  `AbsEntry` int NOT NULL AUTO_INCREMENT,
  `Code` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Name` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `F_RefDate` date NOT NULL,
  `T_RefDate` date NOT NULL,
  `F_DueDate` date NOT NULL,
  `T_DueDate` date NOT NULL,
  `F_TaxDate` date DEFAULT NULL,
  `T_TaxDate` date DEFAULT NULL,
  `Free2` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Free3` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `SubNum` decimal(6,0) DEFAULT NULL,
  `Free` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Free1` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Addition` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AddNum` decimal(6,0) DEFAULT NULL,
  `Category` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Indicator` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `WasStatChd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PeriodStat` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT 'Unlocked',
  `UserSign2` decimal(6,0) DEFAULT NULL,
  PRIMARY KEY (`AbsEntry`)
) ENGINE=InnoDB AUTO_INCREMENT=25 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OHEM`
--

DROP TABLE IF EXISTS `OHEM`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OHEM` (
  `empID` int NOT NULL AUTO_INCREMENT,
  `lastName` varchar(50) NOT NULL,
  `firstName` varchar(50) NOT NULL,
  `middleName` varchar(50) DEFAULT NULL,
  `sex` char(1) DEFAULT NULL,
  `jobTitle` varchar(100) DEFAULT NULL,
  `type` int DEFAULT NULL,
  `dept` int DEFAULT NULL,
  `branch` int DEFAULT NULL,
  `manager` int DEFAULT NULL,
  `userId` int DEFAULT NULL,
  `salesPrson` int DEFAULT NULL,
  `officeTel` varchar(20) DEFAULT NULL,
  `officeExt` varchar(10) DEFAULT NULL,
  `mobile` varchar(20) DEFAULT NULL,
  `pager` varchar(20) DEFAULT NULL,
  `homeTel` varchar(20) DEFAULT NULL,
  `fax` varchar(20) DEFAULT NULL,
  `email` varchar(100) DEFAULT NULL,
  `workStreet` varchar(100) DEFAULT NULL,
  `workBlock` varchar(100) DEFAULT NULL,
  `workZip` varchar(20) DEFAULT NULL,
  `workCity` varchar(100) DEFAULT NULL,
  `workCounty` varchar(100) DEFAULT NULL,
  `workCountr` varchar(3) DEFAULT NULL,
  `workState` varchar(3) DEFAULT NULL,
  `WorkBuild` varchar(100) DEFAULT NULL,
  `AddrTypeW` varchar(100) DEFAULT NULL,
  `StreetNoW` varchar(100) DEFAULT NULL,
  `startDate` date DEFAULT NULL,
  `status` char(1) DEFAULT 'Y',
  `termDate` date DEFAULT NULL,
  `termReason` varchar(100) DEFAULT NULL,
  `Active` char(1) DEFAULT 'Y',
  `salary` decimal(19,6) DEFAULT NULL,
  `salaryUnit` char(1) DEFAULT NULL,
  `emplCost` decimal(19,6) DEFAULT NULL,
  `empCostUnt` char(1) DEFAULT NULL,
  `salaryCurr` varchar(3) DEFAULT NULL,
  `empCostCur` varchar(3) DEFAULT NULL,
  `bankCode` varchar(30) DEFAULT NULL,
  `bankBranch` varchar(50) DEFAULT NULL,
  `bankBranNo` varchar(30) DEFAULT NULL,
  `bankAcount` varchar(50) DEFAULT NULL,
  `homeStreet` varchar(100) DEFAULT NULL,
  `homeBlock` varchar(100) DEFAULT NULL,
  `homeZip` varchar(20) DEFAULT NULL,
  `homeCity` varchar(100) DEFAULT NULL,
  `homeCounty` varchar(100) DEFAULT NULL,
  `homeCountr` varchar(3) DEFAULT NULL,
  `homeState` varchar(3) DEFAULT NULL,
  `HomeBuild` varchar(100) DEFAULT NULL,
  `AddrTypeH` varchar(100) DEFAULT NULL,
  `StreetNoH` varchar(100) DEFAULT NULL,
  `birthDate` date DEFAULT NULL,
  `brthCountr` varchar(3) DEFAULT NULL,
  `BirthPlace` varchar(100) DEFAULT NULL,
  `martStatus` char(1) DEFAULT NULL,
  `nChildren` smallint DEFAULT NULL,
  `govID` varchar(20) DEFAULT NULL,
  `citizenshp` varchar(3) DEFAULT NULL,
  `passportNo` varchar(20) DEFAULT NULL,
  `passportEx` date DEFAULT NULL,
  `PassIssue` date DEFAULT NULL,
  `PassIssuer` varchar(100) DEFAULT NULL,
  `position` int DEFAULT NULL,
  `AtcEntry` int DEFAULT NULL,
  `CostCenter` varchar(50) DEFAULT NULL,
  `CompanyNum` varchar(50) DEFAULT NULL,
  `LogInstanc` int DEFAULT NULL,
  `UserSign` smallint DEFAULT NULL,
  `UserSign2` smallint DEFAULT NULL,
  `createDate` date DEFAULT NULL,
  `updateDate` date DEFAULT NULL,
  `UpdateTS` time DEFAULT NULL,
  `DPPStatus` char(1) DEFAULT NULL,
  `DispMidNam` char(1) DEFAULT NULL,
  `NamePos` char(1) DEFAULT NULL,
  `DispComma` char(1) DEFAULT NULL,
  `QualCode` int DEFAULT NULL,
  `PRWebAccss` char(1) DEFAULT NULL,
  `BPLink` varchar(15) DEFAULT NULL,
  `NaturalPer` char(1) DEFAULT NULL,
  PRIMARY KEY (`empID`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OIBQ`
--

DROP TABLE IF EXISTS `OIBQ`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OIBQ` (
  `AbsEntry` int NOT NULL AUTO_INCREMENT,
  `ItemCode` varchar(50) NOT NULL,
  `BinAbs` int NOT NULL,
  `OnHandQty` decimal(19,6) DEFAULT '0.000000',
  `ReservedQt` decimal(19,6) DEFAULT '0.000000',
  `OrderedQty` decimal(19,6) DEFAULT '0.000000',
  `WhsCode` varchar(8) NOT NULL,
  `Freezed` char(1) DEFAULT 'N',
  `FreezeDoc` int DEFAULT NULL,
  PRIMARY KEY (`AbsEntry`),
  KEY `IDX_OIBQ_ItemCode` (`ItemCode`),
  KEY `IDX_OIBQ_BinAbs` (`BinAbs`),
  KEY `IDX_OIBQ_WhsCode` (`WhsCode`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OIGE`
--

DROP TABLE IF EXISTS `OIGE`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OIGE` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` int NOT NULL,
  `Series` int DEFAULT NULL,
  `DocStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'O',
  `CANCELED` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'N',
  `DocDate` date DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `Comments` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci,
  `Reference` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `UserSign` int DEFAULT NULL,
  PRIMARY KEY (`DocEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OIGN`
--

DROP TABLE IF EXISTS `OIGN`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OIGN` (
  `DocEntry` int NOT NULL,
  `DocNum` int DEFAULT NULL,
  `DocType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'N',
  `Handwrtten` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'N',
  `DocStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `DocDueDate` date DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT '0.000000',
  `VatSum` decimal(19,6) DEFAULT '0.000000',
  `VatSumFC` decimal(19,6) DEFAULT '0.000000',
  `DiscPrcnt` decimal(19,6) DEFAULT '0.000000',
  `DiscSum` decimal(19,6) DEFAULT '0.000000',
  `DocTotal` decimal(19,6) DEFAULT '0.000000',
  `DocTotalFC` decimal(19,6) DEFAULT '0.000000',
  `GrosProfit` decimal(19,6) DEFAULT '0.000000',
  `Ref1` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Ref2` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Comments` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `TransId` int DEFAULT NULL,
  `UserSign` smallint DEFAULT NULL,
  `UserSign2` smallint DEFAULT NULL,
  `Series` int DEFAULT NULL,
  `BPLId` int DEFAULT NULL,
  `BPLName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` int DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` int DEFAULT NULL,
  `ToWhsCode` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `UpdInvnt` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'Y',
  `EDocGenTyp` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `EDocNum` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `EDocStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Attachment` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci,
  `AtcEntry` int DEFAULT NULL,
  PRIMARY KEY (`DocEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OINS`
--

DROP TABLE IF EXISTS `OINS`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OINS` (
  `insID` int NOT NULL AUTO_INCREMENT,
  `customer` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `custmrName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `contactCod` int DEFAULT NULL,
  `directCsmr` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `drctCsmNam` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `manufSN` varchar(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `internalSN` varchar(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `warranty` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `wrrntyStrt` date DEFAULT NULL,
  `wrrntyEnd` date DEFAULT NULL,
  `responsVal` int DEFAULT NULL,
  `responsUnt` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `itemCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `itemName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `itemGroup` smallint DEFAULT NULL,
  `manufDate` date DEFAULT NULL,
  `delivery` int DEFAULT NULL,
  `deliveryNo` int DEFAULT NULL,
  `invoice` int DEFAULT NULL,
  `invoiceNum` int DEFAULT NULL,
  `dlvryDate` date DEFAULT NULL,
  `cntctPhone` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `street` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `block` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `zip` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `city` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `machine` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `country` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `state` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `instLction` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `contract` int DEFAULT NULL,
  `cntrctStrt` date DEFAULT NULL,
  `cntrctEnd` date DEFAULT NULL,
  `attachment` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `objType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `logInstanc` int DEFAULT NULL,
  `userSign` smallint DEFAULT NULL,
  `createDate` date DEFAULT NULL,
  `userSign2` smallint DEFAULT NULL,
  `updateDate` date DEFAULT NULL,
  `Building` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `status` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'A',
  `replcIns` int DEFAULT NULL,
  `repByIns` int DEFAULT NULL,
  `technician` int DEFAULT NULL,
  `territory` int DEFAULT NULL,
  `AtcEntry` int DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AddrType` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Instance` int DEFAULT NULL,
  `StreetNo` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BPType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OwnerCode` int DEFAULT NULL,
  `DPPStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `U_FrequencyDays` int DEFAULT '90',
  `img` longblob,
  PRIMARY KEY (`insID`),
  KEY `FK_OINS_Technician` (`technician`),
  CONSTRAINT `FK_OINS_Technician` FOREIGN KEY (`technician`) REFERENCES `OHEM` (`empID`) ON DELETE SET NULL ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=39 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OINV`
--

DROP TABLE IF EXISTS `OINV`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OINV` (
  `DocEntry` int NOT NULL,
  `DocNum` int NOT NULL,
  `DocType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'I',
  `CANCELED` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'N',
  `Handwrtten` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'N',
  `ObjType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT '13',
  `DocStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'O',
  `InvntStat` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'N',
  `DocDate` date DEFAULT NULL,
  `DocDueDate` date DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `AssetDate` date DEFAULT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci NOT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Address` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci,
  `Address2` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `CntctCode` int DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT '0.000000',
  `VatSum` decimal(19,6) DEFAULT '0.000000',
  `DiscPrcnt` decimal(19,6) DEFAULT '0.000000',
  `DiscSum` decimal(19,6) DEFAULT '0.000000',
  `DocCur` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'USD',
  `DocRate` decimal(19,6) DEFAULT '1.000000',
  `PaidToDate` decimal(19,6) DEFAULT '0.000000',
  `GrosProfit` decimal(19,6) DEFAULT '0.000000',
  `TotalExpns` decimal(19,6) DEFAULT '0.000000',
  `SlpCode` int DEFAULT NULL,
  `GroupNum` int DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `OwnerCode` int DEFAULT NULL,
  `Comments` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `LogInstanc` int DEFAULT '0',
  `UserSign` int DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  PRIMARY KEY (`DocEntry`),
  KEY `idx_oinv_docnum` (`DocNum`),
  KEY `idx_oinv_cardcode` (`CardCode`),
  KEY `idx_oinv_date` (`DocDate`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OITB`
--

DROP TABLE IF EXISTS `OITB`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OITB` (
  `ItmsGrpCod` int NOT NULL AUTO_INCREMENT,
  `ItmsGrpNam` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Locked` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `BalInvntAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SaleCostAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransferAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevenuesAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VarianceAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DecreasAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IncreasAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReturnAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpensesAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EURevenuAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EUExpensAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrRevenuAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrExpensAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExmptIncom` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CycleCode` decimal(6,0) DEFAULT NULL,
  `Alert` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceDifAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExchangeAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BalanceAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PurchaseAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PAReturnAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PurchOfsAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShpdGdsAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatRevAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DecresGlAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IncresGlAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `InvntSys` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PlaningSys` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PrcrmntMtd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrdrIntrvl` decimal(6,0) DEFAULT NULL,
  `OrdrMulti` decimal(19,6) DEFAULT NULL,
  `MinOrdrQty` decimal(19,6) DEFAULT NULL,
  `LeadTime` decimal(6,0) DEFAULT NULL,
  `StokRvlAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StkOffsAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WipAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WipVarAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CostRvlAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CstOffsAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpClrAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpOfstAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Object` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `logInstanc` decimal(6,0) DEFAULT NULL,
  `createDate` date DEFAULT NULL,
  `userSign2` decimal(6,0) DEFAULT NULL,
  `updateDate` date DEFAULT NULL,
  `ARCMAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ARCMFrnAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ARCMEUAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ARCMExpAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `APCMAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `APCMFrnAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `APCMEUAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevRetAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ItemClass` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OSvcCode` decimal(6,0) DEFAULT NULL,
  `ISvcCode` decimal(6,0) DEFAULT NULL,
  `ServiceGrp` decimal(6,0) DEFAULT NULL,
  `NCMCode` decimal(6,0) DEFAULT NULL,
  `MatType` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MatGrp` decimal(6,0) DEFAULT NULL,
  `ProductSrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NegStckAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StkInTnAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PurBalAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhICenAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhOCenAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WipOffset` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StockOffst` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`ItmsGrpCod`)
) ENGINE=InnoDB AUTO_INCREMENT=15 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OITM`
--

DROP TABLE IF EXISTS `OITM`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OITM` (
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `OldItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ItemName` varchar(1000) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrgnName` varchar(1000) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ItmsGrpCod` int DEFAULT NULL,
  `CstGrpCode` decimal(6,0) DEFAULT NULL,
  `VatGourpSa` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VATLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PrchseItem` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SellItem` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `InvntItem` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OnHand` decimal(19,6) DEFAULT NULL,
  `IsCommited` decimal(19,6) DEFAULT NULL,
  `OnOrder` decimal(19,6) DEFAULT NULL,
  `IncomeAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExmptIncom` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MaxLevel` decimal(19,6) DEFAULT NULL,
  `DfltWH` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SuppCatNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BuyUnitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumInBuy` decimal(19,6) DEFAULT NULL,
  `ReorderQty` decimal(19,6) DEFAULT NULL,
  `MinLevel` decimal(19,6) DEFAULT NULL,
  `LstEvlPric` decimal(19,6) DEFAULT NULL,
  `LstEvlDate` date DEFAULT NULL,
  `CustomPer` decimal(19,6) DEFAULT NULL,
  `Canceled` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MnufctTime` decimal(6,0) DEFAULT NULL,
  `WholSlsTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RetilrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SpcialDisc` decimal(19,6) DEFAULT NULL,
  `DscountCod` decimal(6,0) DEFAULT NULL,
  `TrackSales` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SalUnitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumInSale` decimal(19,6) DEFAULT NULL,
  `Consig` decimal(19,6) DEFAULT NULL,
  `QueryGroup` decimal(6,0) DEFAULT NULL,
  `Counted` decimal(19,6) DEFAULT NULL,
  `OpenBlnc` decimal(19,6) DEFAULT NULL,
  `EvalSystem` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `FREE` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PicturName` varchar(200) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlncTrnsfr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserText` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CommisPcnt` decimal(19,6) DEFAULT NULL,
  `CommisSum` decimal(19,6) DEFAULT NULL,
  `CommisGrp` decimal(6,0) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TreeQty` decimal(19,6) DEFAULT NULL,
  `LastPurPrc` decimal(19,6) DEFAULT NULL,
  `LastPurCur` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LastPurDat` date DEFAULT NULL,
  `ExitCur` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BasePrice` decimal(19,6) DEFAULT NULL,
  `ExitWH` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssetItem` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WasCounted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ManSerNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SHeight1` decimal(19,6) DEFAULT NULL,
  `SHght1Unit` decimal(6,0) DEFAULT NULL,
  `SHeight2` decimal(19,6) DEFAULT NULL,
  `SHght2Unit` decimal(6,0) DEFAULT NULL,
  `SWidth1` decimal(19,6) DEFAULT NULL,
  `SWdth1Unit` decimal(6,0) DEFAULT NULL,
  `SWidth2` decimal(19,6) DEFAULT NULL,
  `SWdth2Unit` decimal(6,0) DEFAULT NULL,
  `SLength1` decimal(19,6) DEFAULT NULL,
  `SLen1Unit` decimal(6,0) DEFAULT NULL,
  `Slength2` decimal(19,6) DEFAULT NULL,
  `SLen2Unit` decimal(6,0) DEFAULT NULL,
  `SVolume` decimal(19,6) DEFAULT NULL,
  `SVolUnit` decimal(6,0) DEFAULT NULL,
  `SWeight1` decimal(19,6) DEFAULT NULL,
  `SWght1Unit` decimal(6,0) DEFAULT NULL,
  `SWeight2` decimal(19,6) DEFAULT NULL,
  `SWght2Unit` decimal(6,0) DEFAULT NULL,
  `BHeight1` decimal(19,6) DEFAULT NULL,
  `BHght1Unit` decimal(6,0) DEFAULT NULL,
  `BHeight2` decimal(19,6) DEFAULT NULL,
  `BHght2Unit` decimal(6,0) DEFAULT NULL,
  `BWidth1` decimal(19,6) DEFAULT NULL,
  `BWdth1Unit` decimal(6,0) DEFAULT NULL,
  `BWidth2` decimal(19,6) DEFAULT NULL,
  `BWdth2Unit` decimal(6,0) DEFAULT NULL,
  `BLength1` decimal(19,6) DEFAULT NULL,
  `BLen1Unit` decimal(6,0) DEFAULT NULL,
  `Blength2` decimal(19,6) DEFAULT NULL,
  `BLen2Unit` decimal(6,0) DEFAULT NULL,
  `BVolume` decimal(19,6) DEFAULT NULL,
  `BVolUnit` decimal(6,0) DEFAULT NULL,
  `BWeight1` decimal(19,6) DEFAULT NULL,
  `BWght1Unit` decimal(6,0) DEFAULT NULL,
  `BWeight2` decimal(19,6) DEFAULT NULL,
  `BWght2Unit` decimal(6,0) DEFAULT NULL,
  `FixCurrCms` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FirmCode` decimal(6,0) DEFAULT NULL,
  `LstSalDate` date DEFAULT NULL,
  `InvType` int DEFAULT NULL,
  `QryGroup3` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup4` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup5` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup6` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup7` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup8` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup9` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup10` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup11` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup12` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup13` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup14` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup15` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup16` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup17` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup18` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup19` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup20` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup21` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup22` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup23` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup24` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup25` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup26` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup27` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup28` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup29` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup30` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup31` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup32` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup33` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup34` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup35` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup36` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup37` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup38` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup39` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup40` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup41` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup42` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup43` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup44` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup45` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup46` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup47` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup48` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup49` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup50` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup51` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup52` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup53` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup54` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup55` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup56` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup57` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup58` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup59` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup60` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup61` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup62` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup63` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QryGroup64` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `ExportCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SalFactor1` decimal(19,6) DEFAULT NULL,
  `SalFactor2` decimal(19,6) DEFAULT NULL,
  `SalFactor3` decimal(19,6) DEFAULT NULL,
  `SalFactor4` decimal(19,6) DEFAULT NULL,
  `PurFactor1` decimal(19,6) DEFAULT NULL,
  `PurFactor2` decimal(19,6) DEFAULT NULL,
  `PurFactor3` decimal(19,6) DEFAULT NULL,
  `PurFactor4` decimal(19,6) DEFAULT NULL,
  `SalFormula` varchar(40) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PurFormula` varchar(40) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGroupPu` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AvgPrice` decimal(19,6) DEFAULT NULL,
  `PurPackMsr` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PurPackUn` decimal(19,6) DEFAULT NULL,
  `SalPackMsr` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SalPackUn` decimal(19,6) DEFAULT NULL,
  `SCNCounter` decimal(6,0) DEFAULT NULL,
  `ManBtchNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ManOutOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `valid` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT 'Y',
  `validFrom` date DEFAULT NULL,
  `validTo` date DEFAULT NULL,
  `frozenFor` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `frozenFrom` date DEFAULT NULL,
  `frozenTo` date DEFAULT NULL,
  `BlockOut` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ValidComm` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrozenComm` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Deleted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocEntry` decimal(6,0) DEFAULT NULL,
  `ExpensAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrgnInAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipType` decimal(6,0) DEFAULT NULL,
  `GLMethod` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ECInAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrgnExpAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ECExpAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ByWh` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ItemType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WarrntTmpl` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseUnit` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `Phantom` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IssueMthd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FREE1` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PricingPrc` decimal(19,6) DEFAULT NULL,
  `MngMethod` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReorderPnt` decimal(19,6) DEFAULT NULL,
  `InvntryUom` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PlaningSys` tinyint(1) DEFAULT NULL,
  `PrcrmntMtd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrdrIntrvl` decimal(6,0) DEFAULT NULL,
  `OrdrMulti` decimal(19,6) DEFAULT NULL,
  `MinOrdrQty` decimal(19,6) DEFAULT NULL,
  `LeadTime` decimal(6,0) DEFAULT NULL,
  `IndirctTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCodeAR` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCodeAP` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OSvcCode` decimal(6,0) DEFAULT NULL,
  `ISvcCode` decimal(6,0) DEFAULT NULL,
  `ServiceGrp` decimal(6,0) DEFAULT NULL,
  `NCMCode` decimal(6,0) DEFAULT NULL,
  `MatType` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MatGrp` decimal(6,0) DEFAULT NULL,
  `ProductSrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ServiceCtg` decimal(6,0) DEFAULT NULL,
  `ItemClass` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChapterID` decimal(6,0) DEFAULT NULL,
  `NotifyASN` varchar(40) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ProAssNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `DNFEntry` decimal(6,0) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `Spec` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCtg` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `Number` decimal(6,0) DEFAULT NULL,
  `FuelCode` decimal(6,0) DEFAULT NULL,
  `BeverTblC` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BeverGrpC` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BeverTM` decimal(6,0) DEFAULT NULL,
  `Attachment` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AtcEntry` decimal(6,0) DEFAULT NULL,
  `ToleranDay` decimal(6,0) DEFAULT NULL,
  PRIMARY KEY (`ItemCode`),
  KEY `ItmsGrpCod` (`ItmsGrpCod`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OITW`
--

DROP TABLE IF EXISTS `OITW`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OITW` (
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL DEFAULT '',
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OnHand` decimal(19,6) DEFAULT NULL,
  `IsCommited` decimal(19,6) DEFAULT NULL,
  `OnOrder` decimal(19,6) DEFAULT NULL,
  `Consig` decimal(19,6) DEFAULT NULL,
  `Counted` decimal(19,6) DEFAULT NULL,
  `WasCounted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `MinStock` decimal(19,6) DEFAULT NULL,
  `250Stock` decimal(19,6) DEFAULT NULL,
  `MinOrder` decimal(19,6) DEFAULT NULL,
  `AvgPrice` decimal(19,6) DEFAULT NULL,
  `Locked` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BalInvntAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SaleCostAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransferAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevenuesAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VarianceAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DecreasAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IncreasAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReturnAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpensesAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EURevenuAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EUExpensAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrRevenuAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrExpensAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExmptIncom` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceDifAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExchangeAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BalanceAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PurchaseAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PAReturnAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PurchOfsAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShpdGdsAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatRevAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `DecresGlAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IncresGlAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StokRvlAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StkOffsAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WipAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WipVarAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CostRvlAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CstOffsAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpClrAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpOfstAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Object` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `logInstanc` decimal(6,0) DEFAULT NULL,
  `createDate` date DEFAULT NULL,
  `userSign2` decimal(6,0) DEFAULT NULL,
  `updateDate` date DEFAULT NULL,
  `ARCMAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ARCMFrnAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ARCMEUAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ARCMExpAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `APCMAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `APCMFrnAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `APCMEUAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevRetAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NegStckAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StkInTnAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PurBalAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhICenAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhOCenAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WipOffset` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StockOffst` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`ItemCode`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OJDT`
--

DROP TABLE IF EXISTS `OJDT`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OJDT` (
  `TransId` int NOT NULL AUTO_INCREMENT,
  `BatchNum` decimal(6,0) DEFAULT NULL,
  `BtfStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseRef` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RefDate` date DEFAULT NULL,
  `Memo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref1` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref2` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreatedBy` decimal(6,0) DEFAULT NULL,
  `LocTotal` decimal(19,6) DEFAULT NULL,
  `FcTotal` decimal(19,6) DEFAULT NULL,
  `SysTotal` decimal(19,6) DEFAULT NULL,
  `TransCode` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrignCurr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransRate` decimal(19,6) DEFAULT NULL,
  `BtfLine` decimal(6,0) DEFAULT NULL,
  `TransCurr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DueDate` date DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `PCAddition` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `RefndRprt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AdjTran` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StornoDate` date DEFAULT NULL,
  `StornoToTr` decimal(6,0) DEFAULT NULL,
  `AutoStorno` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Corisptivi` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `StampTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `Number` decimal(6,0) DEFAULT NULL,
  `AutoVAT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocSeries` decimal(6,0) DEFAULT NULL,
  `FolioPref` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `CreateTime` decimal(6,0) DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReportEU` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Report347` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Printed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocType` varchar(12) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AttNum` decimal(6,0) DEFAULT NULL,
  `GenRegNo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `MatType` decimal(6,0) DEFAULT NULL,
  `Creator` varchar(155) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Approver` varchar(155) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Location` decimal(6,0) DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoWT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `VersionNum` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseTrans` decimal(6,0) DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OperatCode` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref3` varchar(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SSIExmpt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`TransId`)
) ENGINE=InnoDB AUTO_INCREMENT=449 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OMRC`
--

DROP TABLE IF EXISTS `OMRC`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OMRC` (
  `FirmCode` int NOT NULL AUTO_INCREMENT,
  `FirmName` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  PRIMARY KEY (`FirmCode`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OPCH`
--

DROP TABLE IF EXISTS `OPCH`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OPCH` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Printed` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocStatus` tinyint(1) NOT NULL DEFAULT '0',
  `InvntSttus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocDate` date NOT NULL,
  `DocDueDate` date NOT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `DiscSum` decimal(19,6) DEFAULT NULL,
  `DiscSumFC` decimal(19,6) DEFAULT NULL,
  `DocCur` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `PaidToDate` decimal(19,6) DEFAULT NULL,
  `PaidFC` decimal(19,6) DEFAULT NULL,
  `GrosProfit` decimal(19,6) DEFAULT NULL,
  `GrosProfFC` decimal(19,6) DEFAULT NULL,
  `Ref1` varchar(11) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Ref2` varchar(11) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Comments` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TransId` decimal(6,0) DEFAULT NULL,
  `ReceiptNum` decimal(6,0) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `TrnspCode` decimal(6,0) DEFAULT NULL,
  `PartSupply` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Confirmed` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `ImportEnt` decimal(6,0) DEFAULT NULL,
  `CreateTran` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SummryType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `UpdInvnt` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `UpdCardBal` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `InvntDirec` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `ShowSCN` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FatherCard` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `CurSource` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `DiscSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `PaidSys` decimal(19,6) DEFAULT NULL,
  `FatherType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GrosProfSy` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `IsICT` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `Filler` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StampNum` varchar(16) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `isCrin` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `selfInv` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatPaid` decimal(19,6) DEFAULT NULL,
  `VatPaidFC` decimal(19,6) DEFAULT NULL,
  `VatPaidSys` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `WddStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `draftKey` decimal(6,0) DEFAULT NULL,
  `TotalExpns` decimal(19,6) DEFAULT NULL,
  `TotalExpFC` decimal(19,6) DEFAULT NULL,
  `TotalExpSC` decimal(19,6) DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `Address2` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `Exported` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StationID` decimal(6,0) DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NetProc` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AqcsTax` decimal(19,6) DEFAULT NULL,
  `AqcsTaxFC` decimal(19,6) DEFAULT NULL,
  `AqcsTaxSC` decimal(19,6) DEFAULT NULL,
  `CashDiscPr` decimal(19,6) DEFAULT NULL,
  `CashDiscnt` decimal(19,6) DEFAULT NULL,
  `CashDiscFC` decimal(19,6) DEFAULT NULL,
  `CashDiscSC` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PaymentRef` varchar(27) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `RoundDif` decimal(19,6) DEFAULT NULL,
  `RoundDifFC` decimal(19,6) DEFAULT NULL,
  `RoundDifSy` decimal(19,6) DEFAULT NULL,
  `CheckDigit` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Form1099` decimal(6,0) DEFAULT NULL,
  `Box1099` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `submitted` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PoPrss` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Rounding` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RevisionPo` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Segment` decimal(6,0) DEFAULT NULL,
  `ReqDate` date DEFAULT NULL,
  `CancelDate` date DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Pick` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PeyMethod` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PayBlock` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `MaxDscn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Reserve` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Max1099` decimal(19,6) DEFAULT NULL,
  `CntrlBnk` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PickRmrk` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ISRCodLine` varchar(53) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ExpAppl` decimal(19,6) DEFAULT NULL,
  `ExpApplFC` decimal(19,6) DEFAULT NULL,
  `ExpApplSC` decimal(19,6) DEFAULT NULL,
  `Project` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LetterNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FromDate` date DEFAULT NULL,
  `ToDate` date DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BoeReserev` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AgentCode` varchar(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `Installmnt` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NnSbAmnt` decimal(19,6) DEFAULT NULL,
  `NnSbAmntSC` decimal(19,6) DEFAULT NULL,
  `NbSbAmntFC` decimal(19,6) DEFAULT NULL,
  `ExepAmnt` decimal(19,6) DEFAULT NULL,
  `ExepAmntSC` decimal(19,6) DEFAULT NULL,
  `ExepAmntFC` decimal(19,6) DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `CorrExt` varchar(25) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CorrInv` decimal(6,0) DEFAULT NULL,
  `NCorrInv` decimal(6,0) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `CtlAccount` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VATRegNum` varchar(12) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TxInvRptNo` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TxInvRptDt` date DEFAULT NULL,
  `KVVATCode` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WTDetails` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SumAbsId` decimal(6,0) DEFAULT NULL,
  `SumRptDate` date DEFAULT NULL,
  `PIndicator` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ManualNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `NnSbVAt` decimal(19,6) DEFAULT NULL,
  `NnSbVAtSC` decimal(19,6) DEFAULT NULL,
  `NbSbVAtFC` decimal(19,6) DEFAULT NULL,
  `ExptVAt` decimal(19,6) DEFAULT NULL,
  `ExptVAtSC` decimal(19,6) DEFAULT NULL,
  `ExptVAtFC` decimal(19,6) DEFAULT NULL,
  `LYPmtAt` decimal(19,6) DEFAULT NULL,
  `LYPmtAtSC` decimal(19,6) DEFAULT NULL,
  `LYPmtAtFC` decimal(19,6) DEFAULT NULL,
  `ExpAnSum` decimal(19,6) DEFAULT NULL,
  `ExpAnSys` decimal(19,6) DEFAULT NULL,
  `ExpAnFrgn` decimal(19,6) DEFAULT NULL,
  `DocSubType` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DpmStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DpmAmnt` decimal(19,6) DEFAULT NULL,
  `DpmAmntSC` decimal(19,6) DEFAULT NULL,
  `DpmAmntFC` decimal(19,6) DEFAULT NULL,
  `DpmDrawn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DpmPrcnt` decimal(19,6) DEFAULT NULL,
  `PaidSum` decimal(19,6) DEFAULT NULL,
  `PaidSumFc` decimal(19,6) DEFAULT NULL,
  `PaidSumSc` decimal(19,6) DEFAULT NULL,
  `FolioPref` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `DpmAppl` decimal(19,6) DEFAULT NULL,
  `DpmApplFc` decimal(19,6) DEFAULT NULL,
  `DpmApplSc` decimal(19,6) DEFAULT NULL,
  `LPgFolioN` decimal(6,0) DEFAULT NULL,
  `Header` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Footer` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Posted` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `BPChCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BPChCntc` decimal(6,0) DEFAULT NULL,
  `PayToCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IsPaytoBnk` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BnkCntry` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BankCode` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BnkAccount` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BnkBranch` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `isIns` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TrackNo` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VersionNum` varchar(11) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `BPNameOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BillToOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ShipToOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RetInvoice` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `MInvNum` decimal(6,0) DEFAULT NULL,
  `MInvDate` date DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SubStr` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Model` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TaxOnExp` decimal(19,6) DEFAULT NULL,
  `TaxOnExpFc` decimal(19,6) DEFAULT NULL,
  `TaxOnExpSc` decimal(19,6) DEFAULT NULL,
  `TaxOnExAp` decimal(19,6) DEFAULT NULL,
  `TaxOnExApF` decimal(19,6) DEFAULT NULL,
  `TaxOnExApS` decimal(19,6) DEFAULT NULL,
  `LastPmnTyp` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LndCstNum` decimal(6,0) DEFAULT NULL,
  `UseCorrVat` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BlkCredMmo` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OpenForLaC` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Excised` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ExcRefDate` date DEFAULT NULL,
  `ExcRmvTime` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SrvGpPrcnt` decimal(19,6) DEFAULT NULL,
  `DepositNum` decimal(6,0) DEFAULT NULL,
  `CertNum` varchar(31) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DutyStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AutoCrtFlw` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FlwRefDate` date DEFAULT NULL,
  `FlwRefNum` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatJENum` decimal(6,0) DEFAULT NULL,
  `DpmVat` decimal(19,6) DEFAULT NULL,
  `DpmVatFc` decimal(19,6) DEFAULT NULL,
  `DpmVatSc` decimal(19,6) DEFAULT NULL,
  `DpmAppVat` decimal(19,6) DEFAULT NULL,
  `DpmAppVatF` decimal(19,6) DEFAULT NULL,
  `DpmAppVatS` decimal(19,6) DEFAULT NULL,
  `InsurOp347` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IgnRelDoc` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BuildDesc` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`),
  KEY `CardCode` (`CardCode`)
) ENGINE=InnoDB AUTO_INCREMENT=297 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OPDN`
--

DROP TABLE IF EXISTS `OPDN`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OPDN` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Printed` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocStatus` tinyint(1) DEFAULT '0',
  `InvntSttus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocDate` date NOT NULL,
  `DocDueDate` date NOT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `DiscSum` decimal(19,6) DEFAULT NULL,
  `DiscSumFC` decimal(19,6) DEFAULT NULL,
  `DocCur` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `PaidToDate` decimal(19,6) DEFAULT NULL,
  `PaidFC` decimal(19,6) DEFAULT NULL,
  `GrosProfit` decimal(19,6) DEFAULT NULL,
  `GrosProfFC` decimal(19,6) DEFAULT NULL,
  `Ref1` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Ref2` varchar(11) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Comments` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TransId` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ReceiptNum` decimal(6,0) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `TrnspCode` decimal(6,0) DEFAULT NULL,
  `PartSupply` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Confirmed` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `ImportEnt` decimal(6,0) DEFAULT NULL,
  `CreateTran` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SummryType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `UpdInvnt` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `UpdCardBal` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `InvntDirec` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `ShowSCN` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FatherCard` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `CurSource` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `DiscSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `PaidSys` decimal(19,6) DEFAULT NULL,
  `FatherType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GrosProfSy` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `IsICT` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `TaxDate` date NOT NULL,
  `Filler` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StampNum` varchar(16) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `isCrin` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `selfInv` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatPaid` decimal(19,6) DEFAULT NULL,
  `VatPaidFC` decimal(19,6) DEFAULT NULL,
  `VatPaidSys` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `WddStatus` tinyint(1) DEFAULT NULL,
  `draftKey` decimal(6,0) DEFAULT NULL,
  `TotalExpns` decimal(19,6) DEFAULT NULL,
  `TotalExpFC` decimal(19,6) DEFAULT NULL,
  `TotalExpSC` decimal(19,6) DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `Address2` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `Exported` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StationID` decimal(6,0) DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NetProc` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AqcsTax` decimal(19,6) DEFAULT NULL,
  `AqcsTaxFC` decimal(19,6) DEFAULT NULL,
  `AqcsTaxSC` decimal(19,6) DEFAULT NULL,
  `CashDiscPr` decimal(19,6) DEFAULT NULL,
  `CashDiscnt` decimal(19,6) DEFAULT NULL,
  `CashDiscFC` decimal(19,6) DEFAULT NULL,
  `CashDiscSC` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PaymentRef` varchar(27) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `RoundDif` decimal(19,6) DEFAULT NULL,
  `RoundDifFC` decimal(19,6) DEFAULT NULL,
  `RoundDifSy` decimal(19,6) DEFAULT NULL,
  `CheckDigit` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Form1099` decimal(6,0) DEFAULT NULL,
  `Box1099` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `submitted` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PoPrss` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Rounding` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RevisionPo` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Segment` decimal(6,0) DEFAULT NULL,
  `ReqDate` date DEFAULT NULL,
  `CancelDate` date DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Pick` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PeyMethod` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PayBlock` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `MaxDscn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Reserve` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Max1099` decimal(19,6) DEFAULT NULL,
  `CntrlBnk` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PickRmrk` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ISRCodLine` varchar(53) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ExpAppl` decimal(19,6) DEFAULT NULL,
  `ExpApplFC` decimal(19,6) DEFAULT NULL,
  `ExpApplSC` decimal(19,6) DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LetterNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FromDate` date DEFAULT NULL,
  `ToDate` date DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BoeReserev` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AgentCode` varchar(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `Installmnt` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NnSbAmnt` decimal(19,6) DEFAULT NULL,
  `NnSbAmntSC` decimal(19,6) DEFAULT NULL,
  `NbSbAmntFC` decimal(19,6) DEFAULT NULL,
  `ExepAmnt` decimal(19,6) DEFAULT NULL,
  `ExepAmntSC` decimal(19,6) DEFAULT NULL,
  `ExepAmntFC` decimal(19,6) DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `CorrExt` varchar(25) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CorrInv` decimal(6,0) DEFAULT NULL,
  `NCorrInv` decimal(6,0) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `CtlAccount` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VATRegNum` varchar(12) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TxInvRptNo` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TxInvRptDt` date DEFAULT NULL,
  `KVVATCode` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WTDetails` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SumAbsId` decimal(6,0) DEFAULT NULL,
  `SumRptDate` date DEFAULT NULL,
  `PIndicator` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ManualNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `NnSbVAt` decimal(19,6) DEFAULT NULL,
  `NnSbVAtSC` decimal(19,6) DEFAULT NULL,
  `NbSbVAtFC` decimal(19,6) DEFAULT NULL,
  `ExptVAt` decimal(19,6) DEFAULT NULL,
  `ExptVAtSC` decimal(19,6) DEFAULT NULL,
  `ExptVAtFC` decimal(19,6) DEFAULT NULL,
  `LYPmtAt` decimal(19,6) DEFAULT NULL,
  `LYPmtAtSC` decimal(19,6) DEFAULT NULL,
  `LYPmtAtFC` decimal(19,6) DEFAULT NULL,
  `ExpAnSum` decimal(19,6) DEFAULT NULL,
  `ExpAnSys` decimal(19,6) DEFAULT NULL,
  `ExpAnFrgn` decimal(19,6) DEFAULT NULL,
  `DocSubType` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DpmStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DpmAmnt` decimal(19,6) DEFAULT NULL,
  `DpmAmntSC` decimal(19,6) DEFAULT NULL,
  `DpmAmntFC` decimal(19,6) DEFAULT NULL,
  `DpmDrawn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DpmPrcnt` decimal(19,6) DEFAULT NULL,
  `PaidSum` decimal(19,6) DEFAULT NULL,
  `PaidSumFc` decimal(19,6) DEFAULT NULL,
  `PaidSumSc` decimal(19,6) DEFAULT NULL,
  `FolioPref` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `DpmAppl` decimal(19,6) DEFAULT NULL,
  `DpmApplFc` decimal(19,6) DEFAULT NULL,
  `DpmApplSc` decimal(19,6) DEFAULT NULL,
  `LPgFolioN` decimal(6,0) DEFAULT NULL,
  `Header` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Footer` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Posted` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `BPChCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BPChCntc` decimal(6,0) DEFAULT NULL,
  `PayToCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IsPaytoBnk` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BnkCntry` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BankCode` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BnkAccount` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BnkBranch` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `isIns` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TrackNo` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VersionNum` varchar(11) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `BPNameOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BillToOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ShipToOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RetInvoice` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `MInvNum` decimal(6,0) DEFAULT NULL,
  `MInvDate` date DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SubStr` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Model` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TaxOnExp` decimal(19,6) DEFAULT NULL,
  `TaxOnExpFc` decimal(19,6) DEFAULT NULL,
  `TaxOnExpSc` decimal(19,6) DEFAULT NULL,
  `TaxOnExAp` decimal(19,6) DEFAULT NULL,
  `TaxOnExApF` decimal(19,6) DEFAULT NULL,
  `TaxOnExApS` decimal(19,6) DEFAULT NULL,
  `LastPmnTyp` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LndCstNum` decimal(6,0) DEFAULT NULL,
  `UseCorrVat` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BlkCredMmo` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OpenForLaC` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Excised` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ExcRefDate` date DEFAULT NULL,
  `ExcRmvTime` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SrvGpPrcnt` decimal(19,6) DEFAULT NULL,
  `DepositNum` decimal(6,0) DEFAULT NULL,
  `CertNum` varchar(31) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DutyStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AutoCrtFlw` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FlwRefDate` date DEFAULT NULL,
  `FlwRefNum` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatJENum` decimal(6,0) DEFAULT NULL,
  `DpmVat` decimal(19,6) DEFAULT NULL,
  `DpmVatFc` decimal(19,6) DEFAULT NULL,
  `DpmVatSc` decimal(19,6) DEFAULT NULL,
  `DpmAppVat` decimal(19,6) DEFAULT NULL,
  `DpmAppVatF` decimal(19,6) DEFAULT NULL,
  `DpmAppVatS` decimal(19,6) DEFAULT NULL,
  `InsurOp347` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IgnRelDoc` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BuildDesc` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Checker` decimal(6,0) DEFAULT NULL,
  `Payee` decimal(6,0) DEFAULT NULL,
  `CopyNumber` decimal(6,0) DEFAULT NULL,
  `SSIExmpt` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PQTGrpSer` decimal(6,0) DEFAULT NULL,
  `PQTGrpNum` decimal(6,0) DEFAULT NULL,
  `PQTGrpHW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ReopOriDoc` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ReopManCls` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DocManClsd` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`),
  KEY `DocNum` (`DocNum`)
) ENGINE=InnoDB AUTO_INCREMENT=865 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OPDN_A`
--

DROP TABLE IF EXISTS `OPDN_A`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OPDN_A` (
  `ID` int NOT NULL AUTO_INCREMENT,
  `name` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `image` longblob,
  `path` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocEntry` int DEFAULT NULL,
  PRIMARY KEY (`ID`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OPLN`
--

DROP TABLE IF EXISTS `OPLN`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OPLN` (
  `ListNum` int NOT NULL AUTO_INCREMENT,
  `ListName` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BASE_NUM` decimal(6,0) DEFAULT NULL,
  `Factor` decimal(19,6) DEFAULT NULL,
  `RoundSys` decimal(6,0) DEFAULT NULL,
  `GroupCode` decimal(6,0) DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SPPCounter` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `IsGrossPrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`ListNum`)
) ENGINE=InnoDB AUTO_INCREMENT=9 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OPOR`
--

DROP TABLE IF EXISTS `OPOR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OPOR` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DocType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Printed` tinyint(1) DEFAULT NULL,
  `DocStatus` tinyint(1) NOT NULL DEFAULT '0',
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocDate` date NOT NULL,
  `DocDueDate` date NOT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `DiscSum` decimal(19,6) DEFAULT NULL,
  `DiscSumFC` decimal(19,6) DEFAULT NULL,
  `DocCur` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `PaidToDate` decimal(19,6) DEFAULT NULL,
  `PaidFC` decimal(19,6) DEFAULT NULL,
  `GrosProfit` decimal(19,6) DEFAULT NULL,
  `GrosProfFC` decimal(19,6) DEFAULT NULL,
  `Ref1` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref2` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Comments` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransId` decimal(6,0) DEFAULT NULL,
  `ReceiptNum` decimal(6,0) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `TrnspCode` decimal(6,0) DEFAULT NULL,
  `PartSupply` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Confirmed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `ImportEnt` decimal(6,0) DEFAULT NULL,
  `CreateTran` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SummryType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdInvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdCardBal` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `InvntDirec` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `ShowSCN` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FatherCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `CurSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `DiscSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `PaidSys` decimal(19,6) DEFAULT NULL,
  `FatherType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrosProfSy` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `IsICT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `Filler` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StampNum` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isCrin` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `UserSign` int DEFAULT NULL,
  `selfInv` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPaid` decimal(19,6) DEFAULT NULL,
  `VatPaidFC` decimal(19,6) DEFAULT NULL,
  `VatPaidSys` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `WddStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT 'W',
  `draftKey` decimal(6,0) DEFAULT NULL,
  `TotalExpns` decimal(19,6) DEFAULT NULL,
  `TotalExpFC` decimal(19,6) DEFAULT NULL,
  `TotalExpSC` decimal(19,6) DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `Address2` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `Exported` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StationID` decimal(6,0) DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NetProc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AqcsTax` decimal(19,6) DEFAULT NULL,
  `AqcsTaxFC` decimal(19,6) DEFAULT NULL,
  `AqcsTaxSC` decimal(19,6) DEFAULT NULL,
  `CashDiscPr` decimal(19,6) DEFAULT NULL,
  `CashDiscnt` decimal(19,6) DEFAULT NULL,
  `CashDiscFC` decimal(19,6) DEFAULT NULL,
  `CashDiscSC` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PaymentRef` varchar(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `RoundDif` decimal(19,6) DEFAULT NULL,
  `RoundDifFC` decimal(19,6) DEFAULT NULL,
  `RoundDifSy` decimal(19,6) DEFAULT NULL,
  `CheckDigit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Form1099` decimal(6,0) DEFAULT NULL,
  `Box1099` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `submitted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoPrss` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rounding` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevisionPo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Segment` decimal(6,0) DEFAULT NULL,
  `ReqDate` date DEFAULT NULL,
  `CancelDate` date DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Pick` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PeyMethod` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `MaxDscn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Reserve` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Max1099` decimal(19,6) DEFAULT NULL,
  `CntrlBnk` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickRmrk` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ISRCodLine` varchar(53) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpAppl` decimal(19,6) DEFAULT NULL,
  `ExpApplFC` decimal(19,6) DEFAULT NULL,
  `ExpApplSC` decimal(19,6) DEFAULT NULL,
  `Project` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LetterNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FromDate` date DEFAULT NULL,
  `ToDate` date DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BoeReserev` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AgentCode` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `Installmnt` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NnSbAmnt` decimal(19,6) DEFAULT NULL,
  `NnSbAmntSC` decimal(19,6) DEFAULT NULL,
  `NbSbAmntFC` decimal(19,6) DEFAULT NULL,
  `ExepAmnt` decimal(19,6) DEFAULT NULL,
  `ExepAmntSC` decimal(19,6) DEFAULT NULL,
  `ExepAmntFC` decimal(19,6) DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `CorrExt` varchar(25) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CorrInv` decimal(6,0) DEFAULT NULL,
  `NCorrInv` decimal(6,0) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `CtlAccount` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VATRegNum` varchar(12) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptDt` date DEFAULT NULL,
  `KVVATCode` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTDetails` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SumAbsId` decimal(6,0) DEFAULT NULL,
  `SumRptDate` date DEFAULT NULL,
  `PIndicator` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ManualNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `NnSbVAt` decimal(19,6) DEFAULT NULL,
  `NnSbVAtSC` decimal(19,6) DEFAULT NULL,
  `NbSbVAtFC` decimal(19,6) DEFAULT NULL,
  `ExptVAt` decimal(19,6) DEFAULT NULL,
  `ExptVAtSC` decimal(19,6) DEFAULT NULL,
  `ExptVAtFC` decimal(19,6) DEFAULT NULL,
  `LYPmtAt` decimal(19,6) DEFAULT NULL,
  `LYPmtAtSC` decimal(19,6) DEFAULT NULL,
  `LYPmtAtFC` decimal(19,6) DEFAULT NULL,
  `ExpAnSum` decimal(19,6) DEFAULT NULL,
  `ExpAnSys` decimal(19,6) DEFAULT NULL,
  `ExpAnFrgn` decimal(19,6) DEFAULT NULL,
  `DocSubType` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmAmnt` decimal(19,6) DEFAULT NULL,
  `DpmAmntSC` decimal(19,6) DEFAULT NULL,
  `DpmAmntFC` decimal(19,6) DEFAULT NULL,
  `DpmDrawn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmPrcnt` decimal(19,6) DEFAULT NULL,
  `PaidSum` decimal(19,6) DEFAULT NULL,
  `PaidSumFc` decimal(19,6) DEFAULT NULL,
  `PaidSumSc` decimal(19,6) DEFAULT NULL,
  `FolioPref` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `DpmAppl` decimal(19,6) DEFAULT NULL,
  `DpmApplFc` decimal(19,6) DEFAULT NULL,
  `DpmApplSc` decimal(19,6) DEFAULT NULL,
  `LPgFolioN` decimal(6,0) DEFAULT NULL,
  `Header` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Footer` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Posted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `BPChCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPChCntc` decimal(6,0) DEFAULT NULL,
  `PayToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsPaytoBnk` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkCntry` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankCode` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkAccount` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkBranch` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isIns` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TrackNo` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VersionNum` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `BPNameOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BillToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RetInvoice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `MInvNum` decimal(6,0) DEFAULT NULL,
  `MInvDate` date DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Model` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxOnExp` decimal(19,6) DEFAULT NULL,
  `TaxOnExpFc` decimal(19,6) DEFAULT NULL,
  `TaxOnExpSc` decimal(19,6) DEFAULT NULL,
  `TaxOnExAp` decimal(19,6) DEFAULT NULL,
  `TaxOnExApF` decimal(19,6) DEFAULT NULL,
  `TaxOnExApS` decimal(19,6) DEFAULT NULL,
  `LastPmnTyp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LndCstNum` decimal(6,0) DEFAULT NULL,
  `UseCorrVat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlkCredMmo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OpenForLaC` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExcRefDate` date DEFAULT NULL,
  `ExcRmvTime` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SrvGpPrcnt` decimal(19,6) DEFAULT NULL,
  `DepositNum` decimal(6,0) DEFAULT NULL,
  `CertNum` varchar(31) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DutyStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoCrtFlw` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FlwRefDate` date DEFAULT NULL,
  `FlwRefNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatJENum` decimal(6,0) DEFAULT NULL,
  `DpmVat` decimal(19,6) DEFAULT NULL,
  `DpmVatFc` decimal(19,6) DEFAULT NULL,
  `DpmVatSc` decimal(19,6) DEFAULT NULL,
  `DpmAppVat` decimal(19,6) DEFAULT NULL,
  `DpmAppVatF` decimal(19,6) DEFAULT NULL,
  `DpmAppVatS` decimal(19,6) DEFAULT NULL,
  `InsurOp347` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IgnRelDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BuildDesc` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Checker` decimal(6,0) DEFAULT NULL,
  `Payee` decimal(6,0) DEFAULT NULL,
  `CopyNumber` decimal(6,0) DEFAULT NULL,
  `SSIExmpt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTGrpSer` decimal(6,0) DEFAULT NULL,
  `PQTGrpNum` decimal(6,0) DEFAULT NULL,
  `PQTGrpHW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopOriDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopManCls` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`),
  UNIQUE KEY `DocNum_UNIQUE` (`DocNum`),
  KEY `FK_OPOR_TO_OCRD_CardCode03ZPU` (`CardCode`),
  KEY `UserSign` (`UserSign`),
  CONSTRAINT `OPOR_ibfk_1` FOREIGN KEY (`UserSign`) REFERENCES `USER` (`USER_ID`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=1112 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OPQT`
--

DROP TABLE IF EXISTS `OPQT`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OPQT` (
  `DocEntry` decimal(6,0) NOT NULL DEFAULT '0',
  `DocNum` int NOT NULL DEFAULT '0',
  `DocType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Printed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocDate` date NOT NULL,
  `DocDueDate` date NOT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `DiscSum` decimal(19,6) DEFAULT NULL,
  `DiscSumFC` decimal(19,6) DEFAULT NULL,
  `DocCur` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `PaidToDate` decimal(19,6) DEFAULT NULL,
  `PaidFC` decimal(19,6) DEFAULT NULL,
  `GrosProfit` decimal(19,6) DEFAULT NULL,
  `GrosProfFC` decimal(19,6) DEFAULT NULL,
  `Ref1` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref2` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Comments` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransId` decimal(6,0) DEFAULT NULL,
  `ReceiptNum` decimal(6,0) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `TrnspCode` decimal(6,0) DEFAULT NULL,
  `PartSupply` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Confirmed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `ImportEnt` decimal(6,0) DEFAULT NULL,
  `CreateTran` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SummryType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdInvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdCardBal` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `InvntDirec` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `ShowSCN` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FatherCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `CurSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `DiscSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `PaidSys` decimal(19,6) DEFAULT NULL,
  `FatherType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrosProfSy` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `IsICT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `Filler` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StampNum` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isCrin` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `selfInv` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPaid` decimal(19,6) DEFAULT NULL,
  `VatPaidFC` decimal(19,6) DEFAULT NULL,
  `VatPaidSys` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `WddStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `draftKey` decimal(6,0) DEFAULT NULL,
  `TotalExpns` decimal(19,6) DEFAULT NULL,
  `TotalExpFC` decimal(19,6) DEFAULT NULL,
  `TotalExpSC` decimal(19,6) DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `Address2` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `Exported` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StationID` decimal(6,0) DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NetProc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AqcsTax` decimal(19,6) DEFAULT NULL,
  `AqcsTaxFC` decimal(19,6) DEFAULT NULL,
  `AqcsTaxSC` decimal(19,6) DEFAULT NULL,
  `CashDiscPr` decimal(19,6) DEFAULT NULL,
  `CashDiscnt` decimal(19,6) DEFAULT NULL,
  `CashDiscFC` decimal(19,6) DEFAULT NULL,
  `CashDiscSC` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PaymentRef` varchar(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `RoundDif` decimal(19,6) DEFAULT NULL,
  `RoundDifFC` decimal(19,6) DEFAULT NULL,
  `RoundDifSy` decimal(19,6) DEFAULT NULL,
  `CheckDigit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Form1099` decimal(6,0) DEFAULT NULL,
  `Box1099` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `submitted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoPrss` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rounding` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevisionPo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Segment` decimal(6,0) DEFAULT NULL,
  `ReqDate` date DEFAULT NULL,
  `CancelDate` date DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Pick` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PeyMethod` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `MaxDscn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Reserve` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Max1099` decimal(19,6) DEFAULT NULL,
  `CntrlBnk` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickRmrk` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ISRCodLine` varchar(53) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpAppl` decimal(19,6) DEFAULT NULL,
  `ExpApplFC` decimal(19,6) DEFAULT NULL,
  `ExpApplSC` decimal(19,6) DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LetterNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FromDate` date DEFAULT NULL,
  `ToDate` date DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BoeReserev` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AgentCode` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `Installmnt` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NnSbAmnt` decimal(19,6) DEFAULT NULL,
  `NnSbAmntSC` decimal(19,6) DEFAULT NULL,
  `NbSbAmntFC` decimal(19,6) DEFAULT NULL,
  `ExepAmnt` decimal(19,6) DEFAULT NULL,
  `ExepAmntSC` decimal(19,6) DEFAULT NULL,
  `ExepAmntFC` decimal(19,6) DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `CorrExt` varchar(25) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CorrInv` decimal(6,0) DEFAULT NULL,
  `NCorrInv` decimal(6,0) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `CtlAccount` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VATRegNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptDt` date DEFAULT NULL,
  `KVVATCode` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTDetails` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SumAbsId` decimal(6,0) DEFAULT NULL,
  `SumRptDate` date DEFAULT NULL,
  `PIndicator` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ManualNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `NnSbVAt` decimal(19,6) DEFAULT NULL,
  `NnSbVAtSC` decimal(19,6) DEFAULT NULL,
  `NbSbVAtFC` decimal(19,6) DEFAULT NULL,
  `ExptVAt` decimal(19,6) DEFAULT NULL,
  `ExptVAtSC` decimal(19,6) DEFAULT NULL,
  `ExptVAtFC` decimal(19,6) DEFAULT NULL,
  `LYPmtAt` decimal(19,6) DEFAULT NULL,
  `LYPmtAtSC` decimal(19,6) DEFAULT NULL,
  `LYPmtAtFC` decimal(19,6) DEFAULT NULL,
  `ExpAnSum` decimal(19,6) DEFAULT NULL,
  `ExpAnSys` decimal(19,6) DEFAULT NULL,
  `ExpAnFrgn` decimal(19,6) DEFAULT NULL,
  `DocSubType` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmAmnt` decimal(19,6) DEFAULT NULL,
  `DpmAmntSC` decimal(19,6) DEFAULT NULL,
  `DpmAmntFC` decimal(19,6) DEFAULT NULL,
  `DpmDrawn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmPrcnt` decimal(19,6) DEFAULT NULL,
  `PaidSum` decimal(19,6) DEFAULT NULL,
  `PaidSumFc` decimal(19,6) DEFAULT NULL,
  `PaidSumSc` decimal(19,6) DEFAULT NULL,
  `FolioPref` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `DpmAppl` decimal(19,6) DEFAULT NULL,
  `DpmApplFc` decimal(19,6) DEFAULT NULL,
  `DpmApplSc` decimal(19,6) DEFAULT NULL,
  `LPgFolioN` decimal(6,0) DEFAULT NULL,
  `Header` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Footer` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Posted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `BPChCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPChCntc` decimal(6,0) DEFAULT NULL,
  `PayToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsPaytoBnk` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkCntry` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankCode` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkAccount` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkBranch` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isIns` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TrackNo` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VersionNum` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `BPNameOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BillToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RetInvoice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `MInvNum` decimal(6,0) DEFAULT NULL,
  `MInvDate` date DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Model` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxOnExp` decimal(19,6) DEFAULT NULL,
  `TaxOnExpFc` decimal(19,6) DEFAULT NULL,
  `TaxOnExpSc` decimal(19,6) DEFAULT NULL,
  `TaxOnExAp` decimal(19,6) DEFAULT NULL,
  `TaxOnExApF` decimal(19,6) DEFAULT NULL,
  `TaxOnExApS` decimal(19,6) DEFAULT NULL,
  `LastPmnTyp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LndCstNum` decimal(6,0) DEFAULT NULL,
  `UseCorrVat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlkCredMmo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OpenForLaC` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExcRefDate` date DEFAULT NULL,
  `ExcRmvTime` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SrvGpPrcnt` decimal(19,6) DEFAULT NULL,
  `DepositNum` decimal(6,0) DEFAULT NULL,
  `CertNum` varchar(31) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DutyStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoCrtFlw` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FlwRefDate` date DEFAULT NULL,
  `FlwRefNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatJENum` decimal(6,0) DEFAULT NULL,
  `DpmVat` decimal(19,6) DEFAULT NULL,
  `DpmVatFc` decimal(19,6) DEFAULT NULL,
  `DpmVatSc` decimal(19,6) DEFAULT NULL,
  `DpmAppVat` decimal(19,6) DEFAULT NULL,
  `DpmAppVatF` decimal(19,6) DEFAULT NULL,
  `DpmAppVatS` decimal(19,6) DEFAULT NULL,
  `InsurOp347` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IgnRelDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BuildDesc` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Checker` decimal(6,0) DEFAULT NULL,
  `Payee` decimal(6,0) DEFAULT NULL,
  `CopyNumber` decimal(6,0) DEFAULT NULL,
  `SSIExmpt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTGrpSer` decimal(6,0) DEFAULT NULL,
  `PQTGrpNum` decimal(6,0) DEFAULT NULL,
  `PQTGrpHW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopOriDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopManCls` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ClosingOpt` decimal(6,0) DEFAULT NULL,
  `SpecDate` date DEFAULT NULL,
  `Ordered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NTSApprov` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NTSWebSite` decimal(6,0) DEFAULT NULL,
  `NTSeTaxNo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NTSApprNo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayDuMonth` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExtraMonth` decimal(6,0) DEFAULT NULL,
  `ExtraDays` decimal(6,0) DEFAULT NULL,
  `CdcOffset` decimal(6,0) DEFAULT NULL,
  `SignMsg` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SignDigest` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CertifNum` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `KeyVersion` decimal(6,0) DEFAULT NULL,
  `EDocGenTyp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ESeries` decimal(6,0) DEFAULT NULL,
  `EDocNum` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDocExpFrm` decimal(6,0) DEFAULT NULL,
  `OnlineQuo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `POSEqNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `POSManufSN` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `POSCashN` decimal(6,0) DEFAULT NULL,
  `EDocStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDocCntnt` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDocProces` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDocErrCod` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDocErrMsg` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDocCancel` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDocTest` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EDocPrefix` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CUP` decimal(6,0) DEFAULT NULL,
  `CIG` decimal(6,0) DEFAULT NULL,
  `DpmAsDscnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Attachment` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AtcEntry` decimal(6,0) DEFAULT NULL,
  `SupplCode` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTSRlvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`),
  CONSTRAINT `FK_PQT1_TO_OPQT_DocEntryZW4jz` FOREIGN KEY (`DocEntry`) REFERENCES `PQT1` (`DocEntry`) ON DELETE RESTRICT ON UPDATE RESTRICT
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OPRJ`
--

DROP TABLE IF EXISTS `OPRJ`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OPRJ` (
  `PrjCode` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `PrjName` varchar(200) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Locked` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` varchar(200) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ValidFrom` date NOT NULL,
  `ValidTo` date NOT NULL,
  `Active` tinyint(1) DEFAULT '1',
  PRIMARY KEY (`PrjCode`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OQUT`
--

DROP TABLE IF EXISTS `OQUT`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OQUT` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(50) DEFAULT NULL,
  `DocType` int DEFAULT NULL,
  `CANCELED` char(1) DEFAULT NULL,
  `Handwrtten` char(1) DEFAULT NULL,
  `Printed` char(1) DEFAULT NULL,
  `DocStatus` tinyint(1) NOT NULL DEFAULT '0',
  `InvntSttus` char(1) DEFAULT NULL,
  `Transfered` char(1) DEFAULT NULL,
  `ObjType` varchar(20) DEFAULT NULL,
  `DocDate` date NOT NULL,
  `DocDueDate` date NOT NULL,
  `CardCode` varchar(15) DEFAULT NULL,
  `CardName` varchar(100) DEFAULT NULL,
  `Address` varchar(254) DEFAULT NULL,
  `NumAtCard` varchar(100) DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `DiscSum` decimal(19,6) DEFAULT NULL,
  `DiscSumFC` decimal(19,6) DEFAULT NULL,
  `DocCur` varchar(3) DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `PaidToDate` decimal(19,6) DEFAULT NULL,
  `PaidFC` decimal(19,6) DEFAULT NULL,
  `GrosProfit` decimal(19,6) DEFAULT NULL,
  `GrosProfFC` decimal(19,6) DEFAULT NULL,
  `Ref1` varchar(11) DEFAULT NULL,
  `Ref2` varchar(11) DEFAULT NULL,
  `Comments` varchar(254) DEFAULT NULL,
  `JrnlMemo` varchar(50) DEFAULT NULL,
  `TransId` decimal(6,0) DEFAULT NULL,
  `ReceiptNum` decimal(6,0) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `TrnspCode` decimal(6,0) DEFAULT NULL,
  `PartSupply` char(1) DEFAULT NULL,
  `Confirmed` char(1) DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `ImportEnt` decimal(6,0) DEFAULT NULL,
  `CreateTran` char(1) DEFAULT NULL,
  `SummryType` char(1) DEFAULT NULL,
  `UpdInvnt` char(1) DEFAULT NULL,
  `UpdCardBal` char(1) DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `InvntDirec` char(1) DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `ShowSCN` char(1) DEFAULT NULL,
  `FatherCard` varchar(15) DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `CurSource` char(1) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `DiscSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `PaidSys` decimal(19,6) DEFAULT NULL,
  `FatherType` char(1) DEFAULT NULL,
  `GrosProfSy` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `IsICT` char(1) DEFAULT NULL,
  `CreateDate` date NOT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `TaxDate` date NOT NULL,
  `LeadTime` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) DEFAULT NULL,
  `StampNum` varchar(16) DEFAULT NULL,
  `isCrin` char(1) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `selfInv` char(1) DEFAULT NULL,
  `VatPaid` decimal(19,6) DEFAULT NULL,
  `VatPaidFC` decimal(19,6) DEFAULT NULL,
  `VatPaidSys` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `WddStatus` char(1) DEFAULT NULL,
  `draftKey` decimal(6,0) DEFAULT NULL,
  `TotalExpns` decimal(19,6) DEFAULT NULL,
  `TotalExpFC` decimal(19,6) DEFAULT NULL,
  `TotalExpSC` decimal(19,6) DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `Address2` varchar(254) DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `Exported` char(1) DEFAULT NULL,
  `StationID` decimal(6,0) DEFAULT NULL,
  `Indicator` varchar(2) DEFAULT NULL,
  `NetProc` char(1) DEFAULT NULL,
  `AqcsTax` decimal(19,6) DEFAULT NULL,
  `AqcsTaxFC` decimal(19,6) DEFAULT NULL,
  `AqcsTaxSC` decimal(19,6) DEFAULT NULL,
  `CashDiscPr` decimal(19,6) DEFAULT NULL,
  `CashDiscnt` decimal(19,6) DEFAULT NULL,
  `CashDiscFC` decimal(19,6) DEFAULT NULL,
  `CashDiscSC` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) DEFAULT NULL,
  `LicTradNum` varchar(32) DEFAULT NULL,
  `PaymentRef` varchar(27) DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `RoundDif` decimal(19,6) DEFAULT NULL,
  `RoundDifFC` decimal(19,6) DEFAULT NULL,
  `RoundDifSy` decimal(19,6) DEFAULT NULL,
  `CheckDigit` char(1) DEFAULT NULL,
  `Form1099` decimal(6,0) DEFAULT NULL,
  `Exclusion` text,
  `submitted` char(1) DEFAULT NULL,
  `PoPrss` char(1) DEFAULT NULL,
  `Rounding` char(1) DEFAULT NULL,
  `RevisionPo` char(1) DEFAULT NULL,
  `Segment` decimal(6,0) DEFAULT NULL,
  `ReqDate` date NOT NULL,
  `CancelDate` date DEFAULT NULL,
  `PickStatus` char(1) DEFAULT NULL,
  `Pick` char(1) DEFAULT NULL,
  `BlockDunn` char(1) DEFAULT NULL,
  `PeyMethod` varchar(15) DEFAULT NULL,
  `PayBlock` char(1) DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `MaxDscn` char(1) DEFAULT NULL,
  `Reserve` char(1) DEFAULT NULL,
  `Max1099` decimal(19,6) DEFAULT NULL,
  `CntrlBnk` varchar(15) DEFAULT NULL,
  `PickRmrk` varchar(254) DEFAULT NULL,
  `ISRCodLine` varchar(53) DEFAULT NULL,
  `ExpAppl` decimal(19,6) DEFAULT NULL,
  `ExpApplFC` decimal(19,6) DEFAULT NULL,
  `ExpApplSC` decimal(19,6) DEFAULT NULL,
  `Project` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) DEFAULT NULL,
  `LetterNum` varchar(20) DEFAULT NULL,
  `FromDate` date DEFAULT NULL,
  `ToDate` date DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BoeReserev` char(1) DEFAULT NULL,
  `AgentCode` varchar(32) DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `Installmnt` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) DEFAULT NULL,
  `NnSbAmnt` decimal(19,6) DEFAULT NULL,
  `NnSbAmntSC` decimal(19,6) DEFAULT NULL,
  `NbSbAmntFC` decimal(19,6) DEFAULT NULL,
  `ExepAmnt` decimal(19,6) DEFAULT NULL,
  `ExepAmntSC` decimal(19,6) DEFAULT NULL,
  `ExepAmntFC` decimal(19,6) DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `CorrExt` varchar(25) DEFAULT NULL,
  `CorrInv` decimal(6,0) DEFAULT NULL,
  `NCorrInv` decimal(6,0) DEFAULT NULL,
  `CEECFlag` char(1) DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `CtlAccount` varchar(15) DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` varchar(20) DEFAULT NULL,
  `VATRegNum` varchar(12) DEFAULT NULL,
  `TxInvRptNo` varchar(10) DEFAULT NULL,
  `TxInvRptDt` date DEFAULT NULL,
  `KVVATCode` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTDetails` varchar(100) DEFAULT NULL,
  `SumAbsId` decimal(6,0) DEFAULT NULL,
  `SumRptDate` date DEFAULT NULL,
  `PIndicator` varchar(10) DEFAULT NULL,
  `ManualNum` varchar(20) DEFAULT NULL,
  `UseShpdGd` char(1) DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `NnSbVAt` decimal(19,6) DEFAULT NULL,
  `NnSbVAtSC` decimal(19,6) DEFAULT NULL,
  `NbSbVAtFC` decimal(19,6) DEFAULT NULL,
  `ExptVAt` decimal(19,6) DEFAULT NULL,
  `ExptVAtSC` decimal(19,6) DEFAULT NULL,
  `ExptVAtFC` decimal(19,6) DEFAULT NULL,
  `LYPmtAt` decimal(19,6) DEFAULT NULL,
  `LYPmtAtSC` decimal(19,6) DEFAULT NULL,
  `LYPmtAtFC` decimal(19,6) DEFAULT NULL,
  `ExpAnSum` decimal(19,6) DEFAULT NULL,
  `ExpAnSys` decimal(19,6) DEFAULT NULL,
  `ExpAnFrgn` decimal(19,6) DEFAULT NULL,
  `DocSubType` varchar(2) DEFAULT NULL,
  `DpmStatus` char(1) DEFAULT NULL,
  `DpmAmnt` decimal(19,6) DEFAULT NULL,
  `DpmAmntSC` decimal(19,6) DEFAULT NULL,
  `DpmAmntFC` decimal(19,6) DEFAULT NULL,
  `DpmDrawn` char(1) DEFAULT NULL,
  `DpmPrcnt` decimal(19,6) DEFAULT NULL,
  `PaidSum` decimal(19,6) DEFAULT NULL,
  `PaidSumFc` decimal(19,6) DEFAULT NULL,
  `PaidSumSc` decimal(19,6) DEFAULT NULL,
  `FolioPref` varchar(2) DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `DpmAppl` decimal(19,6) DEFAULT NULL,
  `DpmApplFc` decimal(19,6) DEFAULT NULL,
  `DpmApplSc` decimal(19,6) DEFAULT NULL,
  `LPgFolioN` decimal(6,0) DEFAULT NULL,
  `Header` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Footer` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Posted` char(1) DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `BPChCode` varchar(15) DEFAULT NULL,
  `BPChCntc` decimal(6,0) DEFAULT NULL,
  `PayToCode` varchar(50) DEFAULT NULL,
  `IsPaytoBnk` char(1) DEFAULT NULL,
  `BnkCntry` varchar(3) DEFAULT NULL,
  `BankCode` varchar(30) DEFAULT NULL,
  `BnkAccount` varchar(50) DEFAULT NULL,
  `BnkBranch` varchar(50) DEFAULT NULL,
  `isIns` char(1) DEFAULT NULL,
  `TrackNo` varchar(30) DEFAULT NULL,
  `VersionNum` varchar(11) DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `BPNameOW` char(1) DEFAULT NULL,
  `BillToOW` char(1) DEFAULT NULL,
  `ShipToOW` char(1) DEFAULT NULL,
  `RetInvoice` char(1) DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `MInvNum` decimal(6,0) DEFAULT NULL,
  `MInvDate` date DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) DEFAULT NULL,
  `SubStr` varchar(3) DEFAULT NULL,
  `ScopeWork` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxOnExp` decimal(19,6) DEFAULT NULL,
  `TaxOnExpFc` decimal(19,6) DEFAULT NULL,
  `TaxOnExpSc` decimal(19,6) DEFAULT NULL,
  `TaxOnExAp` decimal(19,6) DEFAULT NULL,
  `TaxOnExApF` decimal(19,6) DEFAULT NULL,
  `TaxOnExApS` decimal(19,6) DEFAULT NULL,
  `LastPmnTyp` char(1) DEFAULT NULL,
  `LndCstNum` decimal(6,0) DEFAULT NULL,
  `UseCorrVat` char(1) DEFAULT NULL,
  `BlkCredMmo` char(1) DEFAULT NULL,
  `OpenForLaC` char(1) DEFAULT NULL,
  `Excised` char(1) DEFAULT NULL,
  `ExcRefDate` date DEFAULT NULL,
  `ExcRmvTime` varchar(8) DEFAULT NULL,
  `SrvGpPrcnt` decimal(19,6) DEFAULT NULL,
  `DepositNum` decimal(6,0) DEFAULT NULL,
  `CertNum` varchar(31) DEFAULT NULL,
  `DutyStatus` char(1) DEFAULT NULL,
  `AutoCrtFlw` char(1) DEFAULT NULL,
  `FlwRefDate` date DEFAULT NULL,
  `FlwRefNum` varchar(100) DEFAULT NULL,
  `VatJENum` decimal(6,0) DEFAULT NULL,
  `DpmVat` decimal(19,6) DEFAULT NULL,
  `DpmVatFc` decimal(19,6) DEFAULT NULL,
  `DpmVatSc` decimal(19,6) DEFAULT NULL,
  `DpmAppVat` decimal(19,6) DEFAULT NULL,
  `DpmAppVatF` decimal(19,6) DEFAULT NULL,
  `DpmAppVatS` decimal(19,6) DEFAULT NULL,
  `InsurOp347` char(1) DEFAULT NULL,
  `IgnRelDoc` char(1) DEFAULT NULL,
  `BuildDesc` varchar(50) DEFAULT NULL,
  `ResidenNum` char(1) DEFAULT NULL,
  PRIMARY KEY (`DocEntry`),
  UNIQUE KEY `DocNum_UNIQUE` (`DocNum`)
) ENGINE=InnoDB AUTO_INCREMENT=1076 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `ORDN`
--

DROP TABLE IF EXISTS `ORDN`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `ORDN` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Printed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocStatus` tinyint(1) NOT NULL DEFAULT '0',
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `DocDueDate` date DEFAULT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `DiscSum` decimal(19,6) DEFAULT NULL,
  `DiscSumFC` decimal(19,6) DEFAULT NULL,
  `DocCur` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `PaidToDate` decimal(19,6) DEFAULT NULL,
  `PaidFC` decimal(19,6) DEFAULT NULL,
  `GrosProfit` decimal(19,6) DEFAULT NULL,
  `GrosProfFC` decimal(19,6) DEFAULT NULL,
  `Ref1` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref2` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Comments` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransId` decimal(6,0) DEFAULT NULL,
  `ReceiptNum` decimal(6,0) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `TrnspCode` decimal(6,0) DEFAULT NULL,
  `PartSupply` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Confirmed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `ImportEnt` decimal(6,0) DEFAULT NULL,
  `CreateTran` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SummryType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdInvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdCardBal` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `InvntDirec` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `ShowSCN` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FatherCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `CurSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `DiscSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `PaidSys` decimal(19,6) DEFAULT NULL,
  `FatherType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrosProfSy` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `IsICT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `Filler` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StampNum` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isCrin` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `selfInv` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPaid` decimal(19,6) DEFAULT NULL,
  `VatPaidFC` decimal(19,6) DEFAULT NULL,
  `VatPaidSys` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `WddStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `draftKey` decimal(6,0) DEFAULT NULL,
  `TotalExpns` decimal(19,6) DEFAULT NULL,
  `TotalExpFC` decimal(19,6) DEFAULT NULL,
  `TotalExpSC` decimal(19,6) DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `Address2` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `Exported` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StationID` decimal(6,0) DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NetProc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AqcsTax` decimal(19,6) DEFAULT NULL,
  `AqcsTaxFC` decimal(19,6) DEFAULT NULL,
  `AqcsTaxSC` decimal(19,6) DEFAULT NULL,
  `CashDiscPr` decimal(19,6) DEFAULT NULL,
  `CashDiscnt` decimal(19,6) DEFAULT NULL,
  `CashDiscFC` decimal(19,6) DEFAULT NULL,
  `CashDiscSC` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PaymentRef` varchar(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `RoundDif` decimal(19,6) DEFAULT NULL,
  `RoundDifFC` decimal(19,6) DEFAULT NULL,
  `RoundDifSy` decimal(19,6) DEFAULT NULL,
  `CheckDigit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Form1099` decimal(6,0) DEFAULT NULL,
  `Box1099` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `submitted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoPrss` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rounding` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevisionPo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Segment` decimal(6,0) DEFAULT NULL,
  `ReqDate` date DEFAULT NULL,
  `CancelDate` date DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Pick` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PeyMethod` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `MaxDscn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Reserve` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Max1099` decimal(19,6) DEFAULT NULL,
  `CntrlBnk` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickRmrk` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ISRCodLine` varchar(53) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpAppl` decimal(19,6) DEFAULT NULL,
  `ExpApplFC` decimal(19,6) DEFAULT NULL,
  `ExpApplSC` decimal(19,6) DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LetterNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FromDate` date DEFAULT NULL,
  `ToDate` date DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BoeReserev` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AgentCode` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `Installmnt` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NnSbAmnt` decimal(19,6) DEFAULT NULL,
  `NnSbAmntSC` decimal(19,6) DEFAULT NULL,
  `NbSbAmntFC` decimal(19,6) DEFAULT NULL,
  `ExepAmnt` decimal(19,6) DEFAULT NULL,
  `ExepAmntSC` decimal(19,6) DEFAULT NULL,
  `ExepAmntFC` decimal(19,6) DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `CorrExt` varchar(25) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CorrInv` decimal(6,0) DEFAULT NULL,
  `NCorrInv` decimal(6,0) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `CtlAccount` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VATRegNum` varchar(12) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptDt` date DEFAULT NULL,
  `KVVATCode` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTDetails` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SumAbsId` decimal(6,0) DEFAULT NULL,
  `SumRptDate` date DEFAULT NULL,
  `PIndicator` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ManualNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `NnSbVAt` decimal(19,6) DEFAULT NULL,
  `NnSbVAtSC` decimal(19,6) DEFAULT NULL,
  `NbSbVAtFC` decimal(19,6) DEFAULT NULL,
  `ExptVAt` decimal(19,6) DEFAULT NULL,
  `ExptVAtSC` decimal(19,6) DEFAULT NULL,
  `ExptVAtFC` decimal(19,6) DEFAULT NULL,
  `LYPmtAt` decimal(19,6) DEFAULT NULL,
  `LYPmtAtSC` decimal(19,6) DEFAULT NULL,
  `LYPmtAtFC` decimal(19,6) DEFAULT NULL,
  `ExpAnSum` decimal(19,6) DEFAULT NULL,
  `ExpAnSys` decimal(19,6) DEFAULT NULL,
  `ExpAnFrgn` decimal(19,6) DEFAULT NULL,
  `DocSubType` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmAmnt` decimal(19,6) DEFAULT NULL,
  `DpmAmntSC` decimal(19,6) DEFAULT NULL,
  `DpmAmntFC` decimal(19,6) DEFAULT NULL,
  `DpmDrawn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmPrcnt` decimal(19,6) DEFAULT NULL,
  `PaidSum` decimal(19,6) DEFAULT NULL,
  `PaidSumFc` decimal(19,6) DEFAULT NULL,
  `PaidSumSc` decimal(19,6) DEFAULT NULL,
  `FolioPref` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `DpmAppl` decimal(19,6) DEFAULT NULL,
  `DpmApplFc` decimal(19,6) DEFAULT NULL,
  `DpmApplSc` decimal(19,6) DEFAULT NULL,
  `LPgFolioN` decimal(6,0) DEFAULT NULL,
  `Header` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Footer` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Posted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `BPChCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPChCntc` decimal(6,0) DEFAULT NULL,
  `PayToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsPaytoBnk` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkCntry` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankCode` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkAccount` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkBranch` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isIns` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TrackNo` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VersionNum` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `BPNameOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BillToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RetInvoice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `MInvNum` decimal(6,0) DEFAULT NULL,
  `MInvDate` date DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Model` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxOnExp` decimal(19,6) DEFAULT NULL,
  `TaxOnExpFc` decimal(19,6) DEFAULT NULL,
  `TaxOnExpSc` decimal(19,6) DEFAULT NULL,
  `TaxOnExAp` decimal(19,6) DEFAULT NULL,
  `TaxOnExApF` decimal(19,6) DEFAULT NULL,
  `TaxOnExApS` decimal(19,6) DEFAULT NULL,
  `LastPmnTyp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LndCstNum` decimal(6,0) DEFAULT NULL,
  `UseCorrVat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlkCredMmo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OpenForLaC` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExcRefDate` date DEFAULT NULL,
  `ExcRmvTime` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SrvGpPrcnt` decimal(19,6) DEFAULT NULL,
  `DepositNum` decimal(6,0) DEFAULT NULL,
  `CertNum` varchar(31) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DutyStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoCrtFlw` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FlwRefDate` date DEFAULT NULL,
  `FlwRefNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatJENum` decimal(6,0) DEFAULT NULL,
  `DpmVat` decimal(19,6) DEFAULT NULL,
  `DpmVatFc` decimal(19,6) DEFAULT NULL,
  `DpmVatSc` decimal(19,6) DEFAULT NULL,
  `DpmAppVat` decimal(19,6) DEFAULT NULL,
  `DpmAppVatF` decimal(19,6) DEFAULT NULL,
  `DpmAppVatS` decimal(19,6) DEFAULT NULL,
  `InsurOp347` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IgnRelDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BuildDesc` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Checker` decimal(6,0) DEFAULT NULL,
  `Payee` decimal(6,0) DEFAULT NULL,
  `CopyNumber` decimal(6,0) DEFAULT NULL,
  `SSIExmpt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTGrpSer` decimal(6,0) DEFAULT NULL,
  `PQTGrpNum` decimal(6,0) DEFAULT NULL,
  `PQTGrpHW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopOriDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopManCls` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `ORDR`
--

DROP TABLE IF EXISTS `ORDR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `ORDR` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Printed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocStatus` tinyint(1) DEFAULT '0',
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `DocDueDate` date DEFAULT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `DiscSum` decimal(19,6) DEFAULT NULL,
  `DiscSumFC` decimal(19,6) DEFAULT NULL,
  `DocCur` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `PaidToDate` decimal(19,6) DEFAULT NULL,
  `PaidFC` decimal(19,6) DEFAULT NULL,
  `GrosProfit` decimal(19,6) DEFAULT NULL,
  `GrosProfFC` decimal(19,6) DEFAULT NULL,
  `Ref1` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref2` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Comments` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransId` decimal(6,0) DEFAULT NULL,
  `ReceiptNum` decimal(6,0) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `TrnspCode` decimal(6,0) DEFAULT NULL,
  `PartSupply` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Confirmed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `ImportEnt` decimal(6,0) DEFAULT NULL,
  `CreateTran` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SummryType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdInvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdCardBal` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `InvntDirec` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `ShowSCN` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FatherCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `CurSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `DiscSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `PaidSys` decimal(19,6) DEFAULT NULL,
  `FatherType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrosProfSy` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `IsICT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `LeadTime` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StampNum` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isCrin` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `selfInv` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPaid` decimal(19,6) DEFAULT NULL,
  `VatPaidFC` decimal(19,6) DEFAULT NULL,
  `VatPaidSys` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `WddStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `draftKey` decimal(6,0) DEFAULT NULL,
  `TotalExpns` decimal(19,6) DEFAULT NULL,
  `TotalExpFC` decimal(19,6) DEFAULT NULL,
  `TotalExpSC` decimal(19,6) DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `Address2` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `Exported` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StationID` decimal(6,0) DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NetProc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AqcsTax` decimal(19,6) DEFAULT NULL,
  `AqcsTaxFC` decimal(19,6) DEFAULT NULL,
  `AqcsTaxSC` decimal(19,6) DEFAULT NULL,
  `CashDiscPr` decimal(19,6) DEFAULT NULL,
  `CashDiscnt` decimal(19,6) DEFAULT NULL,
  `CashDiscFC` decimal(19,6) DEFAULT NULL,
  `CashDiscSC` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PaymentRef` varchar(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `RoundDif` decimal(19,6) DEFAULT NULL,
  `RoundDifFC` decimal(19,6) DEFAULT NULL,
  `RoundDifSy` decimal(19,6) DEFAULT NULL,
  `CheckDigit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Form1099` decimal(6,0) DEFAULT NULL,
  `Exclusion` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `submitted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoPrss` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rounding` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevisionPo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Segment` decimal(6,0) DEFAULT NULL,
  `ReqDate` date DEFAULT NULL,
  `CancelDate` date DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Pick` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PeyMethod` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `MaxDscn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Reserve` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Max1099` decimal(19,6) DEFAULT NULL,
  `CntrlBnk` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickRmrk` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ISRCodLine` varchar(53) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpAppl` decimal(19,6) DEFAULT NULL,
  `ExpApplFC` decimal(19,6) DEFAULT NULL,
  `ExpApplSC` decimal(19,6) DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LetterNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FromDate` date DEFAULT NULL,
  `ToDate` date DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BoeReserev` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AgentCode` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `Installmnt` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NnSbAmnt` decimal(19,6) DEFAULT NULL,
  `NnSbAmntSC` decimal(19,6) DEFAULT NULL,
  `NbSbAmntFC` decimal(19,6) DEFAULT NULL,
  `ExepAmnt` decimal(19,6) DEFAULT NULL,
  `ExepAmntSC` decimal(19,6) DEFAULT NULL,
  `ExepAmntFC` decimal(19,6) DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `CorrExt` varchar(25) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CorrInv` decimal(6,0) DEFAULT NULL,
  `NCorrInv` decimal(6,0) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `CtlAccount` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VATRegNum` varchar(12) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptDt` date DEFAULT NULL,
  `KVVATCode` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTDetails` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SumAbsId` decimal(6,0) DEFAULT NULL,
  `SumRptDate` date DEFAULT NULL,
  `PIndicator` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ManualNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `NnSbVAt` decimal(19,6) DEFAULT NULL,
  `NnSbVAtSC` decimal(19,6) DEFAULT NULL,
  `NbSbVAtFC` decimal(19,6) DEFAULT NULL,
  `ExptVAt` decimal(19,6) DEFAULT NULL,
  `ExptVAtSC` decimal(19,6) DEFAULT NULL,
  `ExptVAtFC` decimal(19,6) DEFAULT NULL,
  `LYPmtAt` decimal(19,6) DEFAULT NULL,
  `LYPmtAtSC` decimal(19,6) DEFAULT NULL,
  `LYPmtAtFC` decimal(19,6) DEFAULT NULL,
  `ExpAnSum` decimal(19,6) DEFAULT NULL,
  `ExpAnSys` decimal(19,6) DEFAULT NULL,
  `ExpAnFrgn` decimal(19,6) DEFAULT NULL,
  `DocSubType` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmAmnt` decimal(19,6) DEFAULT NULL,
  `DpmAmntSC` decimal(19,6) DEFAULT NULL,
  `DpmAmntFC` decimal(19,6) DEFAULT NULL,
  `DpmDrawn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmPrcnt` decimal(19,6) DEFAULT NULL,
  `PaidSum` decimal(19,6) DEFAULT NULL,
  `PaidSumFc` decimal(19,6) DEFAULT NULL,
  `PaidSumSc` decimal(19,6) DEFAULT NULL,
  `FolioPref` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `DpmAppl` decimal(19,6) DEFAULT NULL,
  `DpmApplFc` decimal(19,6) DEFAULT NULL,
  `DpmApplSc` decimal(19,6) DEFAULT NULL,
  `LPgFolioN` decimal(6,0) DEFAULT NULL,
  `Header` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Footer` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Posted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `BPChCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPChCntc` decimal(6,0) DEFAULT NULL,
  `PayToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsPaytoBnk` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkCntry` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankCode` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkAccount` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkBranch` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isIns` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TrackNo` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VersionNum` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `BPNameOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BillToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RetInvoice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `MInvNum` decimal(6,0) DEFAULT NULL,
  `MInvDate` date DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ScopeWork` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxOnExp` decimal(19,6) DEFAULT NULL,
  `TaxOnExpFc` decimal(19,6) DEFAULT NULL,
  `TaxOnExpSc` decimal(19,6) DEFAULT NULL,
  `TaxOnExAp` decimal(19,6) DEFAULT NULL,
  `TaxOnExApF` decimal(19,6) DEFAULT NULL,
  `TaxOnExApS` decimal(19,6) DEFAULT NULL,
  `LastPmnTyp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LndCstNum` decimal(6,0) DEFAULT NULL,
  `UseCorrVat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlkCredMmo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OpenForLaC` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExcRefDate` date DEFAULT NULL,
  `ExcRmvTime` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SrvGpPrcnt` decimal(19,6) DEFAULT NULL,
  `DepositNum` decimal(6,0) DEFAULT NULL,
  `CertNum` varchar(31) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DutyStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoCrtFlw` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FlwRefDate` date DEFAULT NULL,
  `FlwRefNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatJENum` decimal(6,0) DEFAULT NULL,
  `DpmVat` decimal(19,6) DEFAULT NULL,
  `DpmVatFc` decimal(19,6) DEFAULT NULL,
  `DpmVatSc` decimal(19,6) DEFAULT NULL,
  `DpmAppVat` decimal(19,6) DEFAULT NULL,
  `DpmAppVatF` decimal(19,6) DEFAULT NULL,
  `DpmAppVatS` decimal(19,6) DEFAULT NULL,
  `InsurOp347` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IgnRelDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BuildDesc` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Checker` decimal(6,0) DEFAULT NULL,
  `Payee` decimal(6,0) DEFAULT NULL,
  `CopyNumber` decimal(6,0) DEFAULT NULL,
  `SSIExmpt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTGrpSer` decimal(6,0) DEFAULT NULL,
  `PQTGrpNum` decimal(6,0) DEFAULT NULL,
  `PQTGrpHW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopOriDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopManCls` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`)
) ENGINE=InnoDB AUTO_INCREMENT=569 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `ORIN`
--

DROP TABLE IF EXISTS `ORIN`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `ORIN` (
  `DocEntry` int NOT NULL,
  `DocNum` int NOT NULL,
  `DocType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'N',
  `Handwrtten` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'N',
  `DocStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT '16',
  `DocDate` date DEFAULT NULL,
  `DocDueDate` date DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `CancelDate` date DEFAULT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `PayToCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `DocCur` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT '1.000000',
  `VatPercent` decimal(19,6) DEFAULT '0.000000',
  `VatSum` decimal(19,6) DEFAULT '0.000000',
  `VatSumFC` decimal(19,6) DEFAULT '0.000000',
  `DiscPrcnt` decimal(19,6) DEFAULT '0.000000',
  `DiscSum` decimal(19,6) DEFAULT '0.000000',
  `DocTotal` decimal(19,6) DEFAULT '0.000000',
  `DocTotalFC` decimal(19,6) DEFAULT '0.000000',
  `GrosProfit` decimal(19,6) DEFAULT '0.000000',
  `PaidToDate` decimal(19,6) DEFAULT '0.000000',
  `SlpCode` smallint DEFAULT NULL,
  `TrnspCode` smallint DEFAULT NULL,
  `Ref1` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Ref2` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Comments` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `TransId` int DEFAULT NULL,
  `Series` int DEFAULT NULL,
  `BPLId` int DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT '0.000000',
  `VolUnit` int DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT '0.000000',
  `WeightUnit` int DEFAULT NULL,
  `UserSign` smallint DEFAULT NULL,
  `UserSign2` smallint DEFAULT NULL,
  `LogInstanc` int DEFAULT '0',
  `CreateTS` int DEFAULT NULL,
  `UpdateTS` int DEFAULT NULL,
  `EDocGenTyp` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `EDocNum` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `EDocStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `BPLName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `VATRegNum` varchar(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `ORPD`
--

DROP TABLE IF EXISTS `ORPD`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `ORPD` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `DocType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CANCELED` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Printed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocDate` date NOT NULL,
  `DocDueDate` date NOT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPercent` decimal(19,6) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `DiscSum` decimal(19,6) DEFAULT NULL,
  `DiscSumFC` decimal(19,6) DEFAULT NULL,
  `DocCur` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `PaidToDate` decimal(19,6) DEFAULT NULL,
  `PaidFC` decimal(19,6) DEFAULT NULL,
  `GrosProfit` decimal(19,6) DEFAULT NULL,
  `GrosProfFC` decimal(19,6) DEFAULT NULL,
  `Ref1` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref2` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Comments` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `JrnlMemo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransId` decimal(6,0) DEFAULT NULL,
  `ReceiptNum` decimal(6,0) DEFAULT NULL,
  `GroupNum` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `TrnspCode` decimal(6,0) DEFAULT NULL,
  `PartSupply` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Confirmed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `ImportEnt` decimal(6,0) DEFAULT NULL,
  `CreateTran` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SummryType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdInvnt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UpdCardBal` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `InvntDirec` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `ShowSCN` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FatherCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `CurSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `DiscSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `PaidSys` decimal(19,6) DEFAULT NULL,
  `FatherType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrosProfSy` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `IsICT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight` decimal(19,6) DEFAULT NULL,
  `WeightUnit` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `TaxDate` date NOT NULL,
  `Filler` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StampNum` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isCrin` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `selfInv` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPaid` decimal(19,6) DEFAULT NULL,
  `VatPaidFC` decimal(19,6) DEFAULT NULL,
  `VatPaidSys` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `WddStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `draftKey` decimal(6,0) DEFAULT NULL,
  `TotalExpns` decimal(19,6) DEFAULT NULL,
  `TotalExpFC` decimal(19,6) DEFAULT NULL,
  `TotalExpSC` decimal(19,6) DEFAULT NULL,
  `DunnLevel` decimal(6,0) DEFAULT NULL,
  `Address2` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `Exported` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StationID` decimal(6,0) DEFAULT NULL,
  `Indicator` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NetProc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AqcsTax` decimal(19,6) DEFAULT NULL,
  `AqcsTaxFC` decimal(19,6) DEFAULT NULL,
  `AqcsTaxSC` decimal(19,6) DEFAULT NULL,
  `CashDiscPr` decimal(19,6) DEFAULT NULL,
  `CashDiscnt` decimal(19,6) DEFAULT NULL,
  `CashDiscFC` decimal(19,6) DEFAULT NULL,
  `CashDiscSC` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LicTradNum` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PaymentRef` varchar(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTSum` decimal(19,6) DEFAULT NULL,
  `WTSumFC` decimal(19,6) DEFAULT NULL,
  `WTSumSC` decimal(19,6) DEFAULT NULL,
  `RoundDif` decimal(19,6) DEFAULT NULL,
  `RoundDifFC` decimal(19,6) DEFAULT NULL,
  `RoundDifSy` decimal(19,6) DEFAULT NULL,
  `CheckDigit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Form1099` decimal(6,0) DEFAULT NULL,
  `Box1099` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `submitted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoPrss` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rounding` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevisionPo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Segment` decimal(6,0) DEFAULT NULL,
  `ReqDate` date DEFAULT NULL,
  `CancelDate` date DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Pick` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlockDunn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PeyMethod` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlock` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayBlckRef` decimal(6,0) DEFAULT NULL,
  `MaxDscn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Reserve` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Max1099` decimal(19,6) DEFAULT NULL,
  `CntrlBnk` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickRmrk` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ISRCodLine` varchar(53) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpAppl` decimal(19,6) DEFAULT NULL,
  `ExpApplFC` decimal(19,6) DEFAULT NULL,
  `ExpApplSC` decimal(19,6) DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LetterNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FromDate` date DEFAULT NULL,
  `ToDate` date DEFAULT NULL,
  `WTApplied` decimal(19,6) DEFAULT NULL,
  `WTAppliedF` decimal(19,6) DEFAULT NULL,
  `BoeReserev` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AgentCode` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTAppliedS` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `Installmnt` decimal(6,0) DEFAULT NULL,
  `VATFirst` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NnSbAmnt` decimal(19,6) DEFAULT NULL,
  `NnSbAmntSC` decimal(19,6) DEFAULT NULL,
  `NbSbAmntFC` decimal(19,6) DEFAULT NULL,
  `ExepAmnt` decimal(19,6) DEFAULT NULL,
  `ExepAmntSC` decimal(19,6) DEFAULT NULL,
  `ExepAmntFC` decimal(19,6) DEFAULT NULL,
  `VatDate` date DEFAULT NULL,
  `CorrExt` varchar(25) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CorrInv` decimal(6,0) DEFAULT NULL,
  `NCorrInv` decimal(6,0) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseAmnt` decimal(19,6) DEFAULT NULL,
  `BaseAmntSC` decimal(19,6) DEFAULT NULL,
  `BaseAmntFC` decimal(19,6) DEFAULT NULL,
  `CtlAccount` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VATRegNum` varchar(12) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TxInvRptDt` date DEFAULT NULL,
  `KVVATCode` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WTDetails` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SumAbsId` decimal(6,0) DEFAULT NULL,
  `SumRptDate` date DEFAULT NULL,
  `PIndicator` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ManualNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseShpdGd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseVtAt` decimal(19,6) DEFAULT NULL,
  `BaseVtAtSC` decimal(19,6) DEFAULT NULL,
  `BaseVtAtFC` decimal(19,6) DEFAULT NULL,
  `NnSbVAt` decimal(19,6) DEFAULT NULL,
  `NnSbVAtSC` decimal(19,6) DEFAULT NULL,
  `NbSbVAtFC` decimal(19,6) DEFAULT NULL,
  `ExptVAt` decimal(19,6) DEFAULT NULL,
  `ExptVAtSC` decimal(19,6) DEFAULT NULL,
  `ExptVAtFC` decimal(19,6) DEFAULT NULL,
  `LYPmtAt` decimal(19,6) DEFAULT NULL,
  `LYPmtAtSC` decimal(19,6) DEFAULT NULL,
  `LYPmtAtFC` decimal(19,6) DEFAULT NULL,
  `ExpAnSum` decimal(19,6) DEFAULT NULL,
  `ExpAnSys` decimal(19,6) DEFAULT NULL,
  `ExpAnFrgn` decimal(19,6) DEFAULT NULL,
  `DocSubType` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmAmnt` decimal(19,6) DEFAULT NULL,
  `DpmAmntSC` decimal(19,6) DEFAULT NULL,
  `DpmAmntFC` decimal(19,6) DEFAULT NULL,
  `DpmDrawn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DpmPrcnt` decimal(19,6) DEFAULT NULL,
  `PaidSum` decimal(19,6) DEFAULT NULL,
  `PaidSumFc` decimal(19,6) DEFAULT NULL,
  `PaidSumSc` decimal(19,6) DEFAULT NULL,
  `FolioPref` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FolioNum` decimal(6,0) DEFAULT NULL,
  `DpmAppl` decimal(19,6) DEFAULT NULL,
  `DpmApplFc` decimal(19,6) DEFAULT NULL,
  `DpmApplSc` decimal(19,6) DEFAULT NULL,
  `LPgFolioN` decimal(6,0) DEFAULT NULL,
  `Header` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Footer` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Posted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `BPChCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPChCntc` decimal(6,0) DEFAULT NULL,
  `PayToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsPaytoBnk` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkCntry` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankCode` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkAccount` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BnkBranch` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isIns` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TrackNo` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VersionNum` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LangCode` decimal(6,0) DEFAULT NULL,
  `BPNameOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BillToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RetInvoice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ClsDate` date DEFAULT NULL,
  `MInvNum` decimal(6,0) DEFAULT NULL,
  `MInvDate` date DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubStr` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Model` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxOnExp` decimal(19,6) DEFAULT NULL,
  `TaxOnExpFc` decimal(19,6) DEFAULT NULL,
  `TaxOnExpSc` decimal(19,6) DEFAULT NULL,
  `TaxOnExAp` decimal(19,6) DEFAULT NULL,
  `TaxOnExApF` decimal(19,6) DEFAULT NULL,
  `TaxOnExApS` decimal(19,6) DEFAULT NULL,
  `LastPmnTyp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LndCstNum` decimal(6,0) DEFAULT NULL,
  `UseCorrVat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BlkCredMmo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OpenForLaC` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExcRefDate` date DEFAULT NULL,
  `ExcRmvTime` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SrvGpPrcnt` decimal(19,6) DEFAULT NULL,
  `DepositNum` decimal(6,0) DEFAULT NULL,
  `CertNum` varchar(31) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DutyStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoCrtFlw` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FlwRefDate` date DEFAULT NULL,
  `FlwRefNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatJENum` decimal(6,0) DEFAULT NULL,
  `DpmVat` decimal(19,6) DEFAULT NULL,
  `DpmVatFc` decimal(19,6) DEFAULT NULL,
  `DpmVatSc` decimal(19,6) DEFAULT NULL,
  `DpmAppVat` decimal(19,6) DEFAULT NULL,
  `DpmAppVatF` decimal(19,6) DEFAULT NULL,
  `DpmAppVatS` decimal(19,6) DEFAULT NULL,
  `InsurOp347` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IgnRelDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BuildDesc` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Checker` decimal(6,0) DEFAULT NULL,
  `Payee` decimal(6,0) DEFAULT NULL,
  `CopyNumber` decimal(6,0) DEFAULT NULL,
  `SSIExmpt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTGrpSer` decimal(6,0) DEFAULT NULL,
  `PQTGrpNum` decimal(6,0) DEFAULT NULL,
  `PQTGrpHW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopOriDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReopManCls` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DocStatus` tinyint(1) DEFAULT '0',
  PRIMARY KEY (`DocEntry`)
) ENGINE=InnoDB AUTO_INCREMENT=13 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSCD`
--

DROP TABLE IF EXISTS `OSCD`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSCD` (
  `AbsEntry` decimal(6,0) NOT NULL DEFAULT '0',
  `County` decimal(6,0) DEFAULT NULL,
  `ServiceCD` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Descrip` varchar(70) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Incomimg` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`AbsEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSCG`
--

DROP TABLE IF EXISTS `OSCG`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSCG` (
  `AbsEntry` decimal(6,0) NOT NULL DEFAULT '0',
  `ServiceCtg` varchar(60) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Descrip` varchar(120) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`AbsEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSCL`
--

DROP TABLE IF EXISTS `OSCL`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSCL` (
  `SRID` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `subject` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `subject2` varchar(250) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `subject3` varchar(250) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `subject4` varchar(250) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `customer` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `custmrName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `contctCode` decimal(6,0) DEFAULT NULL,
  `manufSN` varchar(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `internalSN` varchar(32) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `contractID` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `cntrctDate` date DEFAULT NULL,
  `resolDate` date DEFAULT NULL,
  `resolTime` decimal(6,0) DEFAULT NULL,
  `free_1` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `free_2` date DEFAULT NULL,
  `origin` decimal(6,0) DEFAULT NULL,
  `itemCode` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `itemName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `itemGroup` decimal(6,0) DEFAULT NULL,
  `status` int DEFAULT NULL,
  `priority` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `callType` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `equipType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Saves shortcodes: VRF, AHU, CHWFCU, ST, CHILLER',
  `problemTyp` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `problemTyp2` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `problemTyp3` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `problemTyp4` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `assignee` decimal(6,0) DEFAULT NULL,
  `descrption` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `description2` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `description3` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `description4` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `objType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `logInstanc` decimal(6,0) DEFAULT NULL,
  `userSign` decimal(6,0) DEFAULT NULL,
  `createDate` date DEFAULT NULL,
  `createTime` time DEFAULT NULL,
  `closeDate` date DEFAULT NULL,
  `closeTime` decimal(6,0) DEFAULT NULL,
  `userSign2` decimal(6,0) DEFAULT NULL,
  `updateDate` date DEFAULT NULL,
  `VPhHz` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `voltphhz` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `voltphhz2` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `voltphhz3` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `voltphhz4` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `fullLoadAmp` decimal(6,0) DEFAULT NULL,
  `fullLoadAmp2` decimal(10,0) DEFAULT NULL,
  `fullLoadAmp3` decimal(10,0) DEFAULT NULL,
  `fullLoadAmp4` decimal(10,0) DEFAULT NULL,
  `ActualAmp` decimal(6,0) DEFAULT NULL,
  `ActualAmp2` decimal(10,0) DEFAULT NULL,
  `ActualAmp3` decimal(10,0) DEFAULT NULL,
  `ActualAmp4` decimal(10,0) DEFAULT NULL,
  `RefPresHi` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RefPresHi2` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RefPresHi3` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RefPresHi4` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RefPresLow` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RefPresLow2` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RefPresLow3` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RefPresLow4` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WaterPresIn` decimal(6,0) DEFAULT NULL,
  `WaterPresIn2` decimal(10,0) DEFAULT NULL,
  `WaterPresIn3` decimal(10,0) DEFAULT NULL,
  `WaterPresIn4` decimal(10,0) DEFAULT NULL,
  `WaterPresOut` decimal(6,0) DEFAULT NULL,
  `WaterPresOut2` decimal(10,0) DEFAULT NULL,
  `WaterPresOut3` decimal(10,0) DEFAULT NULL,
  `WaterPresOut4` decimal(10,0) DEFAULT NULL,
  `WaterTempIn` decimal(6,0) DEFAULT NULL,
  `WaterTempIn2` decimal(10,0) DEFAULT NULL,
  `WaterTempIn3` decimal(10,0) DEFAULT NULL,
  `WaterTempIn4` decimal(10,0) DEFAULT NULL,
  `WaterTempOut` decimal(6,0) DEFAULT NULL,
  `WaterTempOut2` decimal(10,0) DEFAULT NULL,
  `WaterTempOut3` decimal(10,0) DEFAULT NULL,
  `WaterTempOut4` decimal(10,0) DEFAULT NULL,
  `AmbientTempSup` decimal(6,0) DEFAULT NULL,
  `AmbientTempSup2` decimal(10,0) DEFAULT NULL,
  `AmbientTempSup3` decimal(10,0) DEFAULT NULL,
  `AmbientTempSup4` decimal(10,0) DEFAULT NULL,
  `AmbientTempRet` decimal(6,0) DEFAULT NULL,
  `AmbientTempRet2` decimal(10,0) DEFAULT NULL,
  `AmbientTempRet3` decimal(10,0) DEFAULT NULL,
  `AmbientTempRet4` decimal(10,0) DEFAULT NULL,
  `AmbientTempRoom` decimal(6,0) DEFAULT NULL,
  `AmbientTempRoom2` decimal(10,0) DEFAULT NULL,
  `AmbientTempRoom3` decimal(10,0) DEFAULT NULL,
  `AmbientTempRoom4` decimal(10,0) DEFAULT NULL,
  `insID` decimal(6,0) DEFAULT NULL,
  `technician` varchar(150) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `resolution` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `resolution2` varchar(250) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `resolution3` varchar(250) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `resolution4` varchar(250) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `signature_path` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Brand` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Brand2` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Brand3` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Brand4` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Capacity` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Capacity2` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Capacity3` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Capacity4` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Refrigerant` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Refrigerant2` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Refrigerant3` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Refrigerant4` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OutModel` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OutModel2` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OutModel3` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OutModel4` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OutSerial` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OutSerial2` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OutSerial3` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OutSerial4` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IndoorModel` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IndoorModel2` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IndoorModel3` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IndoorModel4` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IndoorSerial` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IndoorSerial2` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IndoorSerial3` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IndoorSerial4` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `resolOnDat` date DEFAULT NULL,
  `resolOnTim` decimal(6,0) DEFAULT NULL,
  `respByDate` date DEFAULT NULL,
  `respByTime` decimal(6,0) DEFAULT NULL,
  `respOnDate` date DEFAULT NULL,
  `respOnTime` decimal(6,0) DEFAULT NULL,
  `respAssign` decimal(6,0) DEFAULT NULL,
  `AssignDate` date DEFAULT NULL,
  `AssignTime` decimal(6,0) DEFAULT NULL,
  `UpdateTime` decimal(6,0) DEFAULT NULL,
  `responder` decimal(6,0) DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PIndicator` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StartDate` date DEFAULT NULL,
  `StartTime` time DEFAULT NULL,
  `EndDate` date DEFAULT NULL,
  `EndTime` time DEFAULT NULL,
  `Duration` decimal(19,6) DEFAULT NULL,
  `DurType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Reminder` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RemQty` decimal(19,6) DEFAULT NULL,
  `RemType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RemDate` date DEFAULT NULL,
  `RemSent` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `RemTime` decimal(6,0) DEFAULT NULL,
  `Location` decimal(6,0) DEFAULT NULL,
  `AddrName` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AddrType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Street` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `City` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Room` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `State` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Country` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DisplInCal` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SupplCode` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `signature1` longtext CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `signature2` longtext CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `signature3` longtext CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `signature4` longtext CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `acknowledgeby` varchar(150) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `designation` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `technician2` varchar(150) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `technician3` varchar(150) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `technician4` varchar(150) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `driver_name` varchar(150) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `plate_no` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `servicesRendered` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `signedDateTime` timestamp(6) NULL DEFAULT NULL,
  `assignedBy` varchar(45) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RefrigerantUsedID` int DEFAULT NULL,
  `QtyRecovered` decimal(10,2) DEFAULT '0.00',
  `QtyCharged` decimal(10,2) DEFAULT '0.00',
  `client_uuid` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StartLat` decimal(10,8) DEFAULT NULL,
  `StartLong` decimal(11,8) DEFAULT NULL,
  `EndLat` decimal(10,8) DEFAULT NULL,
  `EndLong` decimal(11,8) DEFAULT NULL,
  `CurrentLat` decimal(11,8) DEFAULT NULL,
  `CurrentLong` decimal(11,8) DEFAULT NULL,
  `Remarks` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `U_CustFeedback` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `U_FeedbackScore` int DEFAULT NULL,
  `U_FeedbackDate` datetime DEFAULT NULL,
  `frameworkRef` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ArrivedDate` date DEFAULT NULL,
  `ArrivedTime` time DEFAULT NULL,
  `signedDateTime2` timestamp(6) NULL DEFAULT NULL,
  `signedDateTime3` timestamp(6) NULL DEFAULT NULL,
  `acknowledgeby2` varchar(150) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `designation2` varchar(150) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Lead Technician',
  `acknowledgeby3` varchar(150) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `designation3` varchar(150) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`SRID`),
  KEY `customer` (`customer`),
  KEY `FK_OSCL_Mst_Refrigerants` (`RefrigerantUsedID`),
  KEY `client_uuid` (`client_uuid`),
  CONSTRAINT `FK_OSCL_Mst_Refrigerants` FOREIGN KEY (`RefrigerantUsedID`) REFERENCES `Mst_Refrigerants` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=188 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSCL_DRIVER`
--

DROP TABLE IF EXISTS `OSCL_DRIVER`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSCL_DRIVER` (
  `ID` int NOT NULL AUTO_INCREMENT,
  `SRID` int NOT NULL COMMENT 'Links to the OSCL Service Report Master',
  `DRIVER_ID` int NOT NULL COMMENT 'Links to the USER table',
  `ASSIGNED_BY` int DEFAULT NULL COMMENT 'Tracks the administrator user who dispatched them',
  `ASSIGNED_AT` datetime DEFAULT CURRENT_TIMESTAMP,
  `RELEASED_AT` datetime DEFAULT NULL,
  PRIMARY KEY (`ID`),
  KEY `fk_oscl_driver_srid` (`SRID`),
  KEY `fk_oscl_driver_user` (`DRIVER_ID`),
  CONSTRAINT `fk_oscl_driver_srid` FOREIGN KEY (`SRID`) REFERENCES `OSCL` (`SRID`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `fk_oscl_driver_user` FOREIGN KEY (`DRIVER_ID`) REFERENCES `USER` (`USER_ID`) ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSCL_EquipmentDetails`
--

DROP TABLE IF EXISTS `OSCL_EquipmentDetails`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSCL_EquipmentDetails` (
  `EquipmentID` int NOT NULL AUTO_INCREMENT,
  `SRID` int NOT NULL,
  `Location` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `subject` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `problemTyp` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `descrption` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Brand` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Capacity` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Refrigerant` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OutModel` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OutSerial` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `voltphhz` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `RefPresHi` decimal(6,0) DEFAULT NULL,
  `RefPresLow` decimal(6,0) DEFAULT NULL,
  `WaterPresIn` decimal(6,0) DEFAULT NULL,
  `WaterPresOut` decimal(6,0) DEFAULT NULL,
  `WaterTempIn` decimal(6,0) DEFAULT NULL,
  `WaterTempOut` decimal(6,0) DEFAULT NULL,
  `AmbientTempSup` decimal(6,0) DEFAULT NULL,
  `AmbientTempRet` decimal(6,0) DEFAULT NULL,
  `AmbientTempRoom` decimal(6,0) DEFAULT NULL,
  `resolution` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci,
  `RefrigerantUsedID` int DEFAULT NULL,
  `QtyRecovered` decimal(10,2) DEFAULT '0.00',
  `QtyCharged` decimal(10,2) DEFAULT '0.00',
  `client_uuid` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Recommendation` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `Status` tinyint(1) DEFAULT '1' COMMENT '1 = Active, 0 = Inactive',
  `PartsNeeded` tinyint DEFAULT NULL,
  `PartNeeded_imagepath` varchar(250) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`EquipmentID`),
  KEY `fk_equipment_oscl` (`SRID`),
  KEY `fk_equipment_refrigerant` (`RefrigerantUsedID`),
  KEY `idx_equipment_client_uuid` (`client_uuid`),
  CONSTRAINT `fk_equipment_oscl` FOREIGN KEY (`SRID`) REFERENCES `OSCL` (`SRID`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `fk_equipment_refrigerant` FOREIGN KEY (`RefrigerantUsedID`) REFERENCES `Mst_Refrigerants` (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=319 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSCL_IndoorUnits`
--

DROP TABLE IF EXISTS `OSCL_IndoorUnits`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSCL_IndoorUnits` (
  `IndoorUnitID` int NOT NULL AUTO_INCREMENT,
  `EquipmentID` int NOT NULL,
  `IndoorModel` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IndoorSerial` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Location_Specific` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'e.g., Server Room, Executive Office',
  `client_uuid` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'For Android offline sync idempotency',
  `Status` tinyint(1) DEFAULT '1' COMMENT '1 = Active, 0 = Inactive',
  PRIMARY KEY (`IndoorUnitID`),
  KEY `fk_indoor_equipment` (`EquipmentID`),
  CONSTRAINT `fk_indoor_equipment` FOREIGN KEY (`EquipmentID`) REFERENCES `OSCL_EquipmentDetails` (`EquipmentID`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=1084 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSCL_PerformanceReadings`
--

DROP TABLE IF EXISTS `OSCL_PerformanceReadings`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSCL_PerformanceReadings` (
  `ReadingID` int NOT NULL AUTO_INCREMENT,
  `EquipmentID` int NOT NULL,
  `component_name` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `brand` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `model` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `serial_number` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `full_load_amp` decimal(10,2) DEFAULT '0.00',
  `actual_amp` decimal(10,2) DEFAULT '0.00',
  PRIMARY KEY (`ReadingID`),
  KEY `fk_readings_equipment` (`EquipmentID`),
  CONSTRAINT `fk_readings_equipment` FOREIGN KEY (`EquipmentID`) REFERENCES `OSCL_EquipmentDetails` (`EquipmentID`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=1814 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSCL_TECHNICIAN`
--

DROP TABLE IF EXISTS `OSCL_TECHNICIAN`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSCL_TECHNICIAN` (
  `ID` int NOT NULL AUTO_INCREMENT,
  `SRID` int NOT NULL COMMENT 'Links to Service Report master table',
  `TECH_ID` int NOT NULL COMMENT 'Links to Technician Profile table',
  `ASSIGNED_AT` datetime DEFAULT CURRENT_TIMESTAMP,
  `ASSIGNED_BY` int DEFAULT NULL COMMENT 'USER_ID of dispatcher or creator',
  `IS_PRIMARY` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'N' COMMENT 'Y = Lead Tech on job, N = Crew support member',
  `STATUS` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'ASSIGNED' COMMENT 'ASSIGNED, IN_PROGRESS, COMPLETED, CANCELLED',
  PRIMARY KEY (`ID`),
  UNIQUE KEY `uq_oscl_tech` (`SRID`,`TECH_ID`) COMMENT 'Guarantees a technician cannot be assigned to the same job twice',
  KEY `idx_srid` (`SRID`),
  KEY `idx_tech_id` (`TECH_ID`),
  CONSTRAINT `fk_oscltech_oscl` FOREIGN KEY (`SRID`) REFERENCES `OSCL` (`SRID`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `fk_oscltech_profile` FOREIGN KEY (`TECH_ID`) REFERENCES `TECHNICIAN_PROFILE` (`TECH_ID`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=281 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSCL_TOOL`
--

DROP TABLE IF EXISTS `OSCL_TOOL`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSCL_TOOL` (
  `ID` int NOT NULL AUTO_INCREMENT,
  `SRID` int NOT NULL COMMENT 'Links to OSCL Service Report',
  `ASSET_ID` int NOT NULL COMMENT 'Links to the specific physical item inside TOOL_ITEMS',
  `USER_ID` int DEFAULT NULL COMMENT 'Optional: The specific technician carrying/using the tool',
  `STATUS` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'ASSIGNED' COMMENT 'ASSIGNED, RETURNED, LOST',
  `ASSIGNED_AT` datetime DEFAULT CURRENT_TIMESTAMP,
  `ASSIGNED_BY` int DEFAULT NULL COMMENT 'The dispatcher or warehouse clerk',
  PRIMARY KEY (`ID`),
  UNIQUE KEY `uq_active_asset_srid` (`SRID`,`ASSET_ID`),
  KEY `idx_srid` (`SRID`),
  KEY `idx_asset` (`ASSET_ID`),
  KEY `fk_oscltool_user` (`USER_ID`),
  CONSTRAINT `fk_oscltool_asset` FOREIGN KEY (`ASSET_ID`) REFERENCES `TOOL_ITEMS` (`ASSET_ID`) ON DELETE RESTRICT ON UPDATE CASCADE,
  CONSTRAINT `fk_oscltool_oscl` FOREIGN KEY (`SRID`) REFERENCES `OSCL` (`SRID`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `fk_oscltool_user` FOREIGN KEY (`USER_ID`) REFERENCES `USER` (`USER_ID`) ON DELETE SET NULL ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=62 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSCL_VEHICLE`
--

DROP TABLE IF EXISTS `OSCL_VEHICLE`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSCL_VEHICLE` (
  `ID` int NOT NULL AUTO_INCREMENT,
  `SRID` int NOT NULL COMMENT 'Links to the OSCL Service Report Master table',
  `VEHICLE_ID` int NOT NULL COMMENT 'Links to the VEHICLE_MASTER list',
  `ASSIGNED_BY` int DEFAULT NULL COMMENT 'Links to the USER table tracking who dispatched it',
  `ASSIGNED_AT` datetime DEFAULT CURRENT_TIMESTAMP,
  `RELEASED_AT` datetime DEFAULT NULL COMMENT 'Timestamp when the vehicle returned/was unassigned',
  PRIMARY KEY (`ID`),
  KEY `fk_oscl_vehicle_srid` (`SRID`),
  KEY `fk_oscl_vehicle_master` (`VEHICLE_ID`),
  KEY `fk_oscl_vehicle_user` (`ASSIGNED_BY`),
  CONSTRAINT `fk_oscl_vehicle_master` FOREIGN KEY (`VEHICLE_ID`) REFERENCES `VEHICLE_MASTER` (`VEHICLE_ID`) ON UPDATE CASCADE,
  CONSTRAINT `fk_oscl_vehicle_srid` FOREIGN KEY (`SRID`) REFERENCES `OSCL` (`SRID`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `fk_oscl_vehicle_user` FOREIGN KEY (`ASSIGNED_BY`) REFERENCES `USER` (`USER_ID`) ON DELETE SET NULL ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=33 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSGP`
--

DROP TABLE IF EXISTS `OSGP`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSGP` (
  `AbsEntry` decimal(6,0) NOT NULL DEFAULT '0',
  `ServiceGrp` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Descrip` varchar(70) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `UpdateDate` date NOT NULL,
  PRIMARY KEY (`AbsEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSLP`
--

DROP TABLE IF EXISTS `OSLP`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSLP` (
  `SlpCode` int NOT NULL AUTO_INCREMENT,
  `SlpName` varchar(155) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Memo` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `GroupCode` decimal(6,0) DEFAULT NULL,
  `Locked` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `EmpID` decimal(6,0) DEFAULT NULL,
  PRIMARY KEY (`SlpCode`)
) ENGINE=InnoDB AUTO_INCREMENT=17 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSRI`
--

DROP TABLE IF EXISTS `OSRI`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSRI` (
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SysSerial` decimal(6,0) DEFAULT NULL,
  `SuppSerial` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IntrSerial` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BatchId` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpDate` date NOT NULL,
  `PrdDate` date NOT NULL,
  `InDate` date NOT NULL,
  `GrntStart` date NOT NULL,
  `GrntExp` date NOT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Located` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Notes` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseNum` decimal(6,0) DEFAULT NULL,
  `BaseLinNum` decimal(6,0) DEFAULT NULL,
  `CreateDate` date NOT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ItemName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Status` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Direction` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSRI_DR`
--

DROP TABLE IF EXISTS `OSRI_DR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSRI_DR` (
  `SysSerial` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `DocNum` varchar(20) DEFAULT NULL,
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SuppSerial` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IntrSerial` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BatchId` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpDate` date DEFAULT NULL,
  `PrdDate` date DEFAULT NULL,
  `InDate` date DEFAULT NULL,
  `GrntStart` date DEFAULT NULL,
  `GrntExp` date DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Located` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Notes` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseNum` decimal(6,0) DEFAULT NULL,
  `BaseLinNum` decimal(6,0) DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `CardCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ItemName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Status` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Direction` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  PRIMARY KEY (`SysSerial`),
  KEY `DocEntry` (`DocEntry`),
  CONSTRAINT `OSRI_DR_ibfk_1` FOREIGN KEY (`DocEntry`) REFERENCES `ODLN` (`DocEntry`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=601 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSRN`
--

DROP TABLE IF EXISTS `OSRN`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSRN` (
  `SysNumber` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `DocNum` varchar(20) DEFAULT NULL,
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `itemName` varchar(200) DEFAULT NULL,
  `DistNumber` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MnfSerial` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LotNumber` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpDate` date DEFAULT NULL,
  `MnfDate` date DEFAULT NULL,
  `InDate` date DEFAULT NULL,
  `GrntStart` date DEFAULT NULL,
  `GrntExp` date DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `Location` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Status` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Notes` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  PRIMARY KEY (`SysNumber`),
  KEY `DocEntry` (`DocEntry`)
) ENGINE=InnoDB AUTO_INCREMENT=3509 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSRN_GR`
--

DROP TABLE IF EXISTS `OSRN_GR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSRN_GR` (
  `SysNumber` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `DocNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `itemName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistNumber` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MnfSerial` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LotNumber` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpDate` date DEFAULT NULL,
  `MnfDate` date DEFAULT NULL,
  `InDate` date DEFAULT NULL,
  `GrntStart` date DEFAULT NULL,
  `GrntExp` date DEFAULT NULL,
  `CreateDate` date DEFAULT NULL,
  `Location` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Status` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Notes` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `Transfered` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Instance` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  PRIMARY KEY (`SysNumber`),
  KEY `DocEntry` (`DocEntry`),
  CONSTRAINT `OSRN_GR_ibfk_1` FOREIGN KEY (`DocEntry`) REFERENCES `ORPD` (`DocEntry`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=6 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OSTC`
--

DROP TABLE IF EXISTS `OSTC`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OSTC` (
  `Code` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL DEFAULT '',
  `Name` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `Freight` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `ValidForAR` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ValidForAP` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TfcId` decimal(6,0) DEFAULT NULL,
  `Lock1` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxIcms` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsItmLevel` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CfopIn` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CfopOut` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `UpdateDate` date NOT NULL,
  PRIMARY KEY (`Code`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OUDP`
--

DROP TABLE IF EXISTS `OUDP`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OUDP` (
  `Code` int NOT NULL AUTO_INCREMENT,
  `Name` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Remarks` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  PRIMARY KEY (`Code`)
) ENGINE=InnoDB AUTO_INCREMENT=5 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OUQR`
--

DROP TABLE IF EXISTS `OUQR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OUQR` (
  `IntrnalKey` int DEFAULT NULL COMMENT 'Internal Key',
  `QCategory` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Query Category',
  `QName` varchar(255) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Query Description',
  `QString` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci COMMENT 'Query',
  `QType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Query Type',
  `ColumnSize` int DEFAULT NULL COMMENT 'Column Size',
  `DBType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'DB Type',
  `QLastDate` decimal(10,0) DEFAULT NULL COMMENT 'Last Upload Date',
  `QLastTime` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Last Upload Time',
  `Xslt` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci COMMENT 'XSLT Transformation'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OUSR`
--

DROP TABLE IF EXISTS `OUSR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OUSR` (
  `USERID` int NOT NULL AUTO_INCREMENT,
  `PASSWORD` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PASSWORD1` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PASSWORD2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `INTERNAL_K` decimal(6,0) DEFAULT NULL,
  `USER_CODE` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `U_NAME` varchar(155) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GROUPS` decimal(6,0) DEFAULT NULL,
  `PASSWORD4` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ALLOWENCES` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SUPERUSER` tinyint(1) DEFAULT '0',
  `DISCOUNT` decimal(19,6) DEFAULT NULL,
  `PASSWORD3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Info1File` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Info1Field` decimal(6,0) DEFAULT NULL,
  `Info2File` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Info2Field` decimal(6,0) DEFAULT NULL,
  `Info3File` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Info3Field` decimal(6,0) DEFAULT NULL,
  `Info4File` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Info4Field` decimal(6,0) DEFAULT NULL,
  `dType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `E_Mail` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PortNum` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OutOfOffic` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SendEMail` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SendSMS` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DfltsGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CashLimit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MaxCashSum` decimal(19,6) DEFAULT NULL,
  `Fax` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SendFax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Locked` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Department` int DEFAULT NULL,
  `Branch` decimal(6,0) DEFAULT NULL,
  `UserPrefs` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Language` decimal(6,0) DEFAULT NULL,
  `Charset` decimal(6,0) DEFAULT NULL,
  `OpenCdt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CdtPrvDays` decimal(6,0) DEFAULT NULL,
  `DsplyRates` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AuImpRates` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OpenDps` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RcrFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CheckFiles` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OpenCredit` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CreditDay1` decimal(6,0) DEFAULT NULL,
  `CreditDay2` decimal(6,0) DEFAULT NULL,
  `WallPaper` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WllPprDsp` decimal(6,0) DEFAULT NULL,
  `AdvImagePr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ContactLog` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LastWarned` date DEFAULT NULL,
  `AlertPolFr` decimal(6,0) DEFAULT NULL,
  `ScreenLock` decimal(6,0) DEFAULT NULL,
  `ShowNewMsg` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Picture` varchar(200) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Position` varchar(90) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Country` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Tel1` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Tel2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GENDER` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Birthday` date DEFAULT NULL,
  `EnbMenuFlt` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `objType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `logInstanc` decimal(6,0) DEFAULT NULL,
  `userSign` decimal(6,0) DEFAULT NULL,
  `createDate` date DEFAULT NULL,
  `userSign2` decimal(6,0) DEFAULT NULL,
  `updateDate` date DEFAULT NULL,
  `OneLogPwd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `lastLogin` date DEFAULT NULL,
  `LastPwds` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LastPwds2` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LastPwdSet` date DEFAULT NULL,
  `FailedLog` decimal(6,0) DEFAULT NULL,
  `PwdNeverEx` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SalesDisc` decimal(19,6) DEFAULT NULL,
  `PurchDisc` decimal(19,6) DEFAULT NULL,
  `LstLogoutD` date DEFAULT NULL,
  `LstLoginT` decimal(6,0) DEFAULT NULL,
  `LstLogoutT` decimal(6,0) DEFAULT NULL,
  `LstPwdChT` decimal(6,0) DEFAULT NULL,
  `LstPwdChB` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RclFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MobileUser` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `MobileIMEI` varchar(64) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PrsWkCntEb` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SnapShotId` decimal(6,0) DEFAULT NULL,
  PRIMARY KEY (`USERID`),
  KEY `Department` (`Department`),
  CONSTRAINT `FK_OUSR_TO_OUDP_DepartmeBsBTR` FOREIGN KEY (`Department`) REFERENCES `OUDP` (`Code`) ON DELETE RESTRICT ON UPDATE RESTRICT
) ENGINE=InnoDB AUTO_INCREMENT=2 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OVPM`
--

DROP TABLE IF EXISTS `OVPM`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OVPM` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `DocType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Canceled` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Handwrtten` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Printed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DocDate` date NOT NULL,
  `DocDueDate` date NOT NULL,
  `CardCode` char(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CardName` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address` char(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DdctPrcnt` decimal(19,6) DEFAULT NULL,
  `DdctSum` decimal(19,6) DEFAULT NULL,
  `DdctSumFC` decimal(19,6) DEFAULT NULL,
  `CashAcct` char(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CashSum` decimal(19,6) DEFAULT NULL,
  `CashSumFC` decimal(19,6) DEFAULT NULL,
  `CreditSum` decimal(19,6) DEFAULT NULL,
  `CredSumFC` decimal(19,6) DEFAULT NULL,
  `CheckAcct` char(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CheckSum` decimal(19,6) DEFAULT NULL,
  `CheckSumFC` decimal(19,6) DEFAULT NULL,
  `TrsfrAcct` char(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TrsfrSum` decimal(19,6) DEFAULT NULL,
  `TrsfrSumFC` decimal(19,6) DEFAULT NULL,
  `TrsfrDate` date NOT NULL,
  `TrsfrRef` char(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PayNoDoc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `NoDocSum` decimal(19,6) DEFAULT NULL,
  `NoDocSumFC` decimal(19,6) DEFAULT NULL,
  `DocCurr` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DiffCurr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DocRate` decimal(19,6) DEFAULT NULL,
  `SysRate` decimal(19,6) DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `DocTotalFC` decimal(19,6) DEFAULT NULL,
  `Ref1` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Ref2` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CounterRef` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Comments` char(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `JrnlMemo` char(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransId` decimal(6,0) DEFAULT NULL,
  `DocTime` decimal(6,0) DEFAULT NULL,
  `ShowAtCard` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `SpiltTrans` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `CreateTran` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `CntctCode` decimal(6,0) DEFAULT NULL,
  `DdctSumSy` decimal(19,6) DEFAULT NULL,
  `CashSumSy` decimal(19,6) DEFAULT NULL,
  `CredSumSy` decimal(19,6) DEFAULT NULL,
  `CheckSumSy` decimal(19,6) DEFAULT NULL,
  `TrsfrSumSy` decimal(19,6) DEFAULT NULL,
  `NoDocSumSy` decimal(19,6) DEFAULT NULL,
  `DocTotalSy` decimal(19,6) DEFAULT NULL,
  `ObjType` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StornoRate` decimal(19,6) DEFAULT NULL,
  `UpdateDate` date NOT NULL,
  `CreateDate` date NOT NULL,
  `ApplyVAT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `TaxDate` date NOT NULL,
  `Series` decimal(6,0) DEFAULT NULL,
  `confirmed` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ShowJDT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BankCode` char(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankAcct` char(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `VatGroup` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFC` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `Dcount` decimal(19,6) DEFAULT NULL,
  `DcntSum` decimal(19,6) DEFAULT NULL,
  `DcntSumFC` decimal(19,6) DEFAULT NULL,
  `DcntSumSy` decimal(19,6) DEFAULT NULL,
  `SpltCredLn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PrjCode` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PaymentRef` char(27) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Submitted` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Status` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PayMth` char(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BankCountr` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreightSum` decimal(19,6) DEFAULT NULL,
  `FreigtFC` decimal(19,6) DEFAULT NULL,
  `FreigtSC` decimal(19,6) DEFAULT NULL,
  `BoeAcc` char(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BoeNum` decimal(6,0) DEFAULT NULL,
  `BoeSum` decimal(19,6) DEFAULT NULL,
  `BoeSumFc` decimal(19,6) DEFAULT NULL,
  `BoeSumSc` decimal(19,6) DEFAULT NULL,
  `BoeAgent` char(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BoeStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `WtCode` char(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtSum` decimal(19,6) DEFAULT NULL,
  `WtSumFrgn` decimal(19,6) DEFAULT NULL,
  `WtSumSys` decimal(19,6) DEFAULT NULL,
  `WtAccount` char(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtBaseAmnt` decimal(19,6) DEFAULT NULL,
  `Proforma` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BoeAbs` decimal(6,0) DEFAULT NULL,
  `BpAct` char(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BcgSum` decimal(19,6) DEFAULT NULL,
  `BcgSumFC` decimal(19,6) DEFAULT NULL,
  `BcgSumSy` decimal(19,6) DEFAULT NULL,
  `PIndicator` char(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PaPriority` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PayToCode` char(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IsPaytoBnk` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PBnkCnt` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PBnkCode` char(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PBnkAccnt` char(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PBnkBranch` char(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WizDunBlck` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `WtBaseSum` decimal(19,6) DEFAULT NULL,
  `WtBaseSumF` decimal(19,6) DEFAULT NULL,
  `WtBaseSumS` decimal(19,6) DEFAULT NULL,
  `UndOvDiff` decimal(19,6) DEFAULT NULL,
  `UndOvDiffS` decimal(19,6) DEFAULT NULL,
  `BankActKey` decimal(6,0) DEFAULT NULL,
  `VersionNum` char(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatDate` date NOT NULL,
  `TransCode` char(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PaymType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `TfrRealAmt` decimal(19,6) DEFAULT NULL,
  `CancelDate` date NOT NULL,
  `OpenBal` decimal(19,6) DEFAULT NULL,
  `OpenBalFc` decimal(19,6) DEFAULT NULL,
  `OpenBalSc` decimal(19,6) DEFAULT NULL,
  `BcgTaxSum` decimal(19,6) DEFAULT NULL,
  `BcgTaxSumF` decimal(19,6) DEFAULT NULL,
  `BcgTaxSumS` decimal(19,6) DEFAULT NULL,
  `TpwID` decimal(6,0) DEFAULT NULL,
  `ChallanNo` char(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChallanBak` char(60) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChallanDat` date NOT NULL,
  `WddStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `BcgVatGrp` char(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BcgVatPcnt` decimal(19,6) DEFAULT NULL,
  `SeqCode` decimal(6,0) DEFAULT NULL,
  `Serial` decimal(6,0) DEFAULT NULL,
  `SeriesStr` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubStr` char(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BSRCode` char(25) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `WTOnhldPst` decimal(19,6) DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `BuildDesc` char(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ResidenNum` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `OperatCode` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `UndOvDiffF` decimal(19,6) DEFAULT NULL,
  `MIEntry` decimal(6,0) DEFAULT NULL,
  `FreeText1` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeText2` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeText3` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShowDocNo` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `TDSInterst` decimal(19,6) DEFAULT NULL,
  `TDSCharges` decimal(19,6) DEFAULT NULL,
  `CUP` decimal(6,0) DEFAULT NULL,
  `CIG` decimal(6,0) DEFAULT NULL,
  `MIType` char(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SupplCode` char(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPLId` decimal(6,0) DEFAULT NULL,
  `BPLName` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VATRegNum` char(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OVTG`
--

DROP TABLE IF EXISTS `OVTG`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OVTG` (
  `Code` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL DEFAULT '',
  `Name` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `EffecDate` date DEFAULT NULL,
  `Category` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT 'I - Liable',
  `Account` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Locked` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `IsEC` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Indicator` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcqstnRvrs` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NonDedct` decimal(19,6) DEFAULT NULL,
  `AcqsTax` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GoddsShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NonDedAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPr` decimal(19,6) DEFAULT NULL,
  `ReportCode` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FixdAssts` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CalcMethod` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FixedAmnt` decimal(19,6) DEFAULT NULL,
  `ExtCode` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Correction` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatCrctn` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RetVatCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RepType` decimal(6,0) DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `TaxCtgr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquAccount` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `IsIGIC` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ServSupply` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Inactive` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCtgrBL` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `R349Code` decimal(6,0) DEFAULT NULL,
  PRIMARY KEY (`Code`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OWDD`
--

DROP TABLE IF EXISTS `OWDD`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OWDD` (
  `WddCode` int NOT NULL AUTO_INCREMENT,
  `WtmCode` int DEFAULT NULL,
  `OwnerID` int DEFAULT NULL,
  `DocEntry` int DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DocDate` date NOT NULL,
  `CurrStep` int DEFAULT NULL,
  `Status` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Remarks` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `UserSign` int DEFAULT NULL,
  `CreateDate` date NOT NULL,
  `CreateTime` time DEFAULT NULL,
  `IsDraft` tinyint(1) DEFAULT NULL,
  `MaxReqr` int DEFAULT NULL,
  PRIMARY KEY (`WddCode`),
  UNIQUE KEY `UQ_OWDD_ObjType_DocEntry` (`ObjType`,`DocEntry`),
  KEY `WtmCode` (`WtmCode`),
  KEY `CurrStep` (`CurrStep`),
  KEY `OwnerID` (`OwnerID`),
  KEY `UserSign` (`UserSign`),
  CONSTRAINT `OWDD_ibfk_1` FOREIGN KEY (`WtmCode`) REFERENCES `OWTM` (`WtmCode`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `OWDD_ibfk_2` FOREIGN KEY (`UserSign`) REFERENCES `USER` (`USER_ID`) ON DELETE RESTRICT ON UPDATE CASCADE,
  CONSTRAINT `OWDD_ibfk_3` FOREIGN KEY (`OwnerID`) REFERENCES `USER` (`USER_ID`) ON DELETE RESTRICT ON UPDATE CASCADE,
  CONSTRAINT `OWDD_ibfk_4` FOREIGN KEY (`CurrStep`) REFERENCES `OWST` (`WstCode`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=1893 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OWHS`
--

DROP TABLE IF EXISTS `OWHS`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OWHS` (
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `WhsName` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `Grp_Code` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BalInvntAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SaleCostAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TransferAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Locked` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DataSource` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `RevenuesAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VarianceAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DecreasAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IncreasAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ReturnAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpensesAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EURevenuAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EUExpensAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrRevenuAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FrExpensAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Street` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Block` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ZipCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `City` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `County` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Country` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `State` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Location` decimal(6,0) DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExmptIncom` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UseTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceDifAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExchangeAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BalanceAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PurchaseAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PAReturnAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PurchOfsAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FedTaxID` varchar(32) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Building` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShpdGdsAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatRevAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DecresGlAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `IncresGlAc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Nettable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StokRvlAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StkOffsAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WipAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WipVarAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CostRvlAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CstOffsAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpClrAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExpOfstAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `objType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `logInstanc` decimal(6,0) DEFAULT NULL,
  `createDate` date NOT NULL,
  `userSign2` decimal(6,0) DEFAULT NULL,
  `updateDate` date NOT NULL,
  `ARCMAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ARCMFrnAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ARCMEUAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ARCMExpAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `APCMAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `APCMFrnAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `APCMEUAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RevRetAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BPLid` decimal(6,0) DEFAULT NULL,
  `OwnerCode` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NegStckAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StkInTnAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AddrType` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StreetNo` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PurBalAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhICenAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhOCenAct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhShipTo` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WipOffset` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StockOffst` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StorKeeper` decimal(6,0) DEFAULT NULL,
  `Shipper` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BinActivat` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BinSeptor` varchar(5) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DftBinAbs` decimal(6,0) DEFAULT NULL,
  `DftBinEnfd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoIssMtd` decimal(6,0) DEFAULT NULL,
  `ManageSnB` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RecItemsBy` decimal(6,0) DEFAULT NULL,
  `RecBinEnab` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GlblLocNum` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RecvEmpBin` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Inactive` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Recv250Qty` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AutoRecvMd` decimal(6,0) DEFAULT NULL,
  `Recv250WT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `RecvUpTo` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeChrgSA` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeChrgPU` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxOffice` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address2` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Address3` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `External` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`WhsCode`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OWHT`
--

DROP TABLE IF EXISTS `OWHT`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OWHT` (
  `WTCode` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `WTName` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `EffecDate` date NOT NULL,
  `Category` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL DEFAULT 'Payment',
  `BaseType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `PrctBsAmnt` decimal(19,6) DEFAULT NULL,
  `OffclCode` varchar(4) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Account` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `MinTaxAmt` decimal(19,6) DEFAULT NULL,
  `IsPrgrss` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Type` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `RoundType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `WTTypeId` decimal(6,0) DEFAULT NULL,
  `WTCurrency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `UpdateDate` date DEFAULT NULL,
  `UserSign` decimal(6,0) DEFAULT NULL,
  `Section` decimal(6,0) DEFAULT NULL,
  `Threshold` decimal(19,6) DEFAULT NULL,
  `Surcharge` decimal(19,6) DEFAULT NULL,
  `Concess` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Assessee` decimal(6,0) DEFAULT NULL,
  `ApTdsAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ApSurAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ApCessAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ApHscAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ArTdsAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ArSurAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ArCessAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `ArHscAcc` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Location` decimal(6,0) DEFAULT NULL,
  `ReturnType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `UserSign2` decimal(6,0) DEFAULT NULL,
  `Inactive` tinyint(1) DEFAULT '0',
  `InCSTCode` decimal(6,0) DEFAULT NULL,
  `OutCSTCode` decimal(6,0) DEFAULT NULL,
  `CalBaseN` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`WTCode`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OWST`
--

DROP TABLE IF EXISTS `OWST`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OWST` (
  `WstCode` int NOT NULL AUTO_INCREMENT,
  `Name` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Remarks` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `MaxReqr` int DEFAULT NULL,
  `UserSign` int DEFAULT NULL,
  PRIMARY KEY (`WstCode`),
  KEY `UserSign` (`UserSign`),
  CONSTRAINT `OWST_ibfk_1` FOREIGN KEY (`UserSign`) REFERENCES `USER` (`USER_ID`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=66 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OWTM`
--

DROP TABLE IF EXISTS `OWTM`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OWTM` (
  `WtmCode` int NOT NULL AUTO_INCREMENT,
  `Name` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Remarks` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Conds` tinyint(1) DEFAULT '1',
  `Active` tinyint(1) NOT NULL DEFAULT '1',
  `UserSign` int DEFAULT NULL,
  `PmptChg` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`WtmCode`),
  KEY `UserSign` (`UserSign`),
  CONSTRAINT `OWTM_ibfk_1` FOREIGN KEY (`UserSign`) REFERENCES `USER` (`USER_ID`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=128 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `OWTR`
--

DROP TABLE IF EXISTS `OWTR`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `OWTR` (
  `DocEntry` int NOT NULL AUTO_INCREMENT,
  `DocNum` int NOT NULL,
  `Series` int DEFAULT NULL,
  `DocStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'O',
  `CANCELED` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'N',
  `DocDate` date DEFAULT NULL,
  `TaxDate` date DEFAULT NULL,
  `Filler` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `ToWhsCode` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `DocTotal` decimal(19,6) DEFAULT NULL,
  `Comments` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci,
  `JournalMemo` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `UserSign` int DEFAULT NULL,
  PRIMARY KEY (`DocEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `PCH1`
--

DROP TABLE IF EXISTS `PCH1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `PCH1` (
  `DocEntry` int NOT NULL,
  `DocID` int NOT NULL AUTO_INCREMENT,
  `TargetType` int DEFAULT NULL,
  `TrgetEntry` int DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseType` int DEFAULT NULL,
  `BaseEntry` int DEFAULT NULL,
  `BaseLine` int DEFAULT NULL,
  `LineStatus` tinyint(1) DEFAULT NULL,
  `ItemCode` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Dscription` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SlpCode` int DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` int DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` int DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` int DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` int DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` int DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` int DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` int DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` int DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` int DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` int DEFAULT NULL,
  `Factor1` decimal(19,6) DEFAULT NULL,
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BaseDocNum` int DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` int DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LogInstanc` int DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` int DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` int DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PoLineNum` int DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TaxCode` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` int DEFAULT NULL,
  `TrnsCode` int DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Text` varchar(299) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OwnerCode` int DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `GrossBase` int DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Usage2` int DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CiOppLineN` int DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` int DEFAULT NULL,
  `RG23APart2` int DEFAULT NULL,
  `RG23CPart1` int DEFAULT NULL,
  `RG23CPart2` int DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `LocCode` int DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `PQTReqQty` decimal(19,6) DEFAULT NULL,
  `PQTReqDate` date DEFAULT NULL,
  `PcDocType` int DEFAULT NULL,
  `PcQuantity` decimal(19,6) DEFAULT NULL,
  `LinManClsd` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `VatGrpSrc` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `NoInvtryMv` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `ActBaseEnt` int DEFAULT NULL,
  `ActBaseLn` int DEFAULT NULL,
  `ActBaseNum` int DEFAULT NULL,
  `OpenRtnQty` decimal(19,6) DEFAULT NULL,
  `AgrNo` int DEFAULT NULL,
  `AgrLnNum` int DEFAULT NULL,
  `CredOrigin` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FREE01` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FREE02` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `FREE03` int DEFAULT NULL,
  PRIMARY KEY (`DocID`),
  KEY `DocEntry` (`DocEntry`),
  CONSTRAINT `PCH1_ibfk_1` FOREIGN KEY (`DocEntry`) REFERENCES `OPCH` (`DocEntry`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=385 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `PDN1`
--

DROP TABLE IF EXISTS `PDN1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `PDN1` (
  `DocID` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` decimal(6,0) DEFAULT NULL,
  `LineStatus` tinyint(1) NOT NULL DEFAULT '0',
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Dscription` varchar(200) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` int NOT NULL DEFAULT '0',
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Text` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DUsage` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTReqQty` decimal(19,6) DEFAULT NULL,
  `PQTReqDate` date DEFAULT NULL,
  `PcDocType` decimal(6,0) DEFAULT NULL,
  `PcQuantity` decimal(19,6) DEFAULT NULL,
  `LinManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGrpSrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`DocID`),
  KEY `DocEntry` (`DocEntry`),
  KEY `ItemCode` (`ItemCode`)
) ENGINE=InnoDB AUTO_INCREMENT=4176 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `PM_SCHEDULE`
--

DROP TABLE IF EXISTS `PM_SCHEDULE`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `PM_SCHEDULE` (
  `PM_ID` int NOT NULL AUTO_INCREMENT,
  `EquipmentID` int NOT NULL,
  `FrequencyDays` int DEFAULT '90',
  `LastPerformedDate` date DEFAULT NULL,
  `NextDueDate` date DEFAULT NULL,
  `IsActive` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Y',
  PRIMARY KEY (`PM_ID`),
  KEY `idx_equipment_due` (`EquipmentID`,`NextDueDate`),
  CONSTRAINT `fk_equipment` FOREIGN KEY (`EquipmentID`) REFERENCES `OINS` (`insID`)
) ENGINE=InnoDB AUTO_INCREMENT=68 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `POR1`
--

DROP TABLE IF EXISTS `POR1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `POR1` (
  `DocID` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL DEFAULT '0',
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` decimal(6,0) DEFAULT NULL,
  `LineStatus` tinyint(1) NOT NULL DEFAULT '0',
  `RowNum` int DEFAULT NULL,
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Dscription` varchar(1000) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` int DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` int DEFAULT '0',
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(30) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Text` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DUsage` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTReqQty` decimal(19,6) DEFAULT NULL,
  `PQTReqDate` date DEFAULT NULL,
  `PcDocType` decimal(6,0) DEFAULT NULL,
  `PcQuantity` decimal(19,6) DEFAULT NULL,
  `LinManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGrpSrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubText` varchar(255) COLLATE utf8mb3_unicode_ci DEFAULT NULL COMMENT 'This is for additional text for P.O. Item for Sub Con clients',
  PRIMARY KEY (`DocID`),
  KEY `FK_POR1_TO_OPOR_DocEntryAYJqQ` (`DocEntry`),
  KEY `ItemCode` (`ItemCode`),
  CONSTRAINT `FK_POR1_TO_OPOR_DocEntryAYJqQ` FOREIGN KEY (`DocEntry`) REFERENCES `OPOR` (`DocEntry`) ON DELETE RESTRICT ON UPDATE RESTRICT
) ENGINE=InnoDB AUTO_INCREMENT=1585 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `PQT1`
--

DROP TABLE IF EXISTS `PQT1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `PQT1` (
  `DocEntry` decimal(6,0) NOT NULL DEFAULT '0',
  `LineNum` decimal(6,0) NOT NULL DEFAULT '0',
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` decimal(6,0) DEFAULT NULL,
  `LineStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Dscription` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` decimal(19,6) DEFAULT NULL,
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Text` varchar(250) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Usaged` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTReqQty` decimal(19,6) DEFAULT NULL,
  `PQTReqDate` date DEFAULT NULL,
  `PcDocType` decimal(6,0) DEFAULT NULL,
  `PcQuantity` decimal(19,6) DEFAULT NULL,
  `LinManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGrpSrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NoInvtryMv` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActBaseEnt` decimal(6,0) DEFAULT NULL,
  `ActBaseLn` decimal(6,0) DEFAULT NULL,
  `ActBaseNum` decimal(6,0) DEFAULT NULL,
  `OpenRtnQty` decimal(19,6) DEFAULT NULL,
  `AgrNo` decimal(6,0) DEFAULT NULL,
  `AgrLnNum` decimal(6,0) DEFAULT NULL,
  `CredOrigin` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FREE01` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FREE02` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FREE03` decimal(6,0) DEFAULT NULL,
  PRIMARY KEY (`DocEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `QUT1`
--

DROP TABLE IF EXISTS `QUT1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `QUT1` (
  `DocID` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(16) DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` decimal(6,0) DEFAULT NULL,
  `LineStatus` tinyint(1) DEFAULT '0',
  `ItemCode` varchar(20) DEFAULT NULL,
  `Dscription` varchar(1000) DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) DEFAULT NULL,
  `SerialNum` varchar(17) DEFAULT NULL,
  `WhsCode` varchar(8) DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) DEFAULT NULL,
  `AcctCode` varchar(15) DEFAULT NULL,
  `TaxStatus` char(1) DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) DEFAULT NULL,
  `SubCatNum` varchar(20) DEFAULT NULL,
  `BaseCard` varchar(15) DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) DEFAULT NULL,
  `OcrCode` varchar(8) DEFAULT NULL,
  `Project` varchar(8) DEFAULT NULL,
  `CodeBars` varchar(16) DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` decimal(19,6) DEFAULT NULL,
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) DEFAULT NULL,
  `SWW` varchar(16) DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) DEFAULT NULL,
  `ImportLog` varchar(20) DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) DEFAULT NULL,
  `DropShip` char(1) DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) DEFAULT NULL,
  `TaxCode` varchar(8) DEFAULT NULL,
  `TaxType` char(1) DEFAULT NULL,
  `OrigItem` varchar(20) DEFAULT NULL,
  `BackOrdr` char(1) DEFAULT NULL,
  `FreeTxt` varchar(100) DEFAULT NULL,
  `PickStatus` char(1) DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) DEFAULT NULL,
  `DeferrTax` char(1) DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) DEFAULT NULL,
  `TranType` char(1) DEFAULT NULL,
  `Text` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) DEFAULT NULL,
  `ShipToDesc` varchar(254) DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) DEFAULT NULL,
  `DescOW` char(1) DEFAULT NULL,
  `DetailsOW` char(1) DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) DEFAULT NULL,
  `CSTCode` varchar(6) DEFAULT NULL,
  `Usage1` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) DEFAULT NULL,
  `WtCalced` char(1) DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) DEFAULT NULL,
  `ChgAsmBoMW` char(1) DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) DEFAULT NULL,
  `OcrCode3` varchar(8) DEFAULT NULL,
  `OcrCode4` varchar(8) DEFAULT NULL,
  `OcrCode5` varchar(8) DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) DEFAULT NULL,
  `Excisable` char(1) DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) DEFAULT NULL,
  `CogsOcrCo3` varchar(8) DEFAULT NULL,
  `CogsOcrCo4` varchar(8) DEFAULT NULL,
  `CogsOcrCo5` varchar(8) DEFAULT NULL,
  `LnExcised` char(1) DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) DEFAULT NULL,
  `CSTfIPI` varchar(2) DEFAULT NULL,
  `CSTfPIS` varchar(2) DEFAULT NULL,
  `CSTfCOFINS` varchar(2) DEFAULT NULL,
  `ExLineNo` varchar(10) DEFAULT NULL,
  `isSrvCall` char(1) DEFAULT NULL,
  PRIMARY KEY (`DocID`),
  KEY `QUT1_ibfk_1` (`DocEntry`),
  CONSTRAINT `QUT1_ibfk_1` FOREIGN KEY (`DocEntry`) REFERENCES `OQUT` (`DocEntry`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=2223 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `QUT11`
--

DROP TABLE IF EXISTS `QUT11`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `QUT11` (
  `DocID` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` varchar(20) DEFAULT NULL,
  `LineStatus` tinyint(1) NOT NULL DEFAULT '0',
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Dscription` varchar(1000) DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` decimal(19,6) DEFAULT NULL,
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Text` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Usage1` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`DocID`),
  KEY `DocEntry` (`DocEntry`),
  CONSTRAINT `QUT11_ibfk_1` FOREIGN KEY (`DocEntry`) REFERENCES `OQUT` (`DocEntry`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=8289 DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `RDN1`
--

DROP TABLE IF EXISTS `RDN1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `RDN1` (
  `LineNum` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` decimal(6,0) DEFAULT NULL,
  `LineStatus` tinyint(1) NOT NULL DEFAULT '0',
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Dscription` varchar(1000) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` decimal(19,6) DEFAULT NULL,
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Text` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DUSAGE` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTReqQty` decimal(19,6) DEFAULT NULL,
  `PQTReqDate` date DEFAULT NULL,
  `PcDocType` decimal(6,0) DEFAULT NULL,
  `PcQuantity` decimal(19,6) DEFAULT NULL,
  `LinManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGrpSrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`LineNum`),
  KEY `DocEntry` (`DocEntry`),
  CONSTRAINT `RDN1_ibfk_1` FOREIGN KEY (`DocEntry`) REFERENCES `ORDN` (`DocEntry`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=8 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `RDR1`
--

DROP TABLE IF EXISTS `RDR1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `RDR1` (
  `LineNum` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` decimal(6,0) DEFAULT NULL,
  `LineStatus` tinyint(1) NOT NULL DEFAULT '0',
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Dscription` varchar(1000) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` int NOT NULL DEFAULT '0',
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Text` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DUsage` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTReqQty` decimal(19,6) DEFAULT NULL,
  `PQTReqDate` date DEFAULT NULL,
  `PcDocType` decimal(6,0) DEFAULT NULL,
  `PcQuantity` decimal(19,6) DEFAULT NULL,
  `LinManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGrpSrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`LineNum`),
  KEY `DocEntry` (`DocEntry`),
  CONSTRAINT `RDR1_ibfk_1` FOREIGN KEY (`DocEntry`) REFERENCES `ORDR` (`DocEntry`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=968 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `RDR11`
--

DROP TABLE IF EXISTS `RDR11`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `RDR11` (
  `DocID` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `LineStatus` tinyint(1) NOT NULL DEFAULT '0',
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Dscription` varchar(1000) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` int NOT NULL DEFAULT '0',
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Text` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DUsage` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTReqQty` decimal(19,6) DEFAULT NULL,
  `PQTReqDate` date DEFAULT NULL,
  `PcDocType` decimal(6,0) DEFAULT NULL,
  `PcQuantity` decimal(19,6) DEFAULT NULL,
  `LinManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGrpSrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`DocID`),
  KEY `DocEntry` (`DocEntry`),
  CONSTRAINT `RDR11_ibfk_1` FOREIGN KEY (`DocEntry`) REFERENCES `ORDR` (`DocEntry`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=5658 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `RIN1`
--

DROP TABLE IF EXISTS `RIN1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `RIN1` (
  `DocEntry` int NOT NULL,
  `LineNum` int NOT NULL,
  `TargetType` int DEFAULT NULL,
  `TrgetEntry` int DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `BaseType` int DEFAULT NULL,
  `BaseEntry` int DEFAULT NULL,
  `BaseLine` int DEFAULT NULL,
  `LineStatus` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `ItemCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Dscription` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `CodeBars` varchar(254) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT '0.000000',
  `InvQty` decimal(19,6) DEFAULT '0.000000',
  `OpenQty` decimal(19,6) DEFAULT '0.000000',
  `PackQty` decimal(19,6) DEFAULT '0.000000',
  `Price` decimal(19,6) DEFAULT '0.000000',
  `PriceBefDi` decimal(19,6) DEFAULT '0.000000',
  `DiscPrcnt` decimal(19,6) DEFAULT '0.000000',
  `LineTotal` decimal(19,6) DEFAULT '0.000000',
  `TotalFrgn` decimal(19,6) DEFAULT '0.000000',
  `GTotal` decimal(19,6) DEFAULT '0.000000',
  `StockPrice` decimal(19,6) DEFAULT '0.000000',
  `StockValue` decimal(19,6) DEFAULT '0.000000',
  `DocDate` date DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `TaxCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT '0.000000',
  `VatSum` decimal(19,6) DEFAULT '0.000000',
  `AcctCode` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `OcrCode` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `OcrCode2` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `UomCode` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT 'Y',
  `TreeType` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `FreeTxt` text CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci,
  `ObjType` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT '16',
  PRIMARY KEY (`DocEntry`,`LineNum`),
  CONSTRAINT `FK_RIN1_ORIN` FOREIGN KEY (`DocEntry`) REFERENCES `ORIN` (`DocEntry`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `RPD1`
--

DROP TABLE IF EXISTS `RPD1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `RPD1` (
  `LineNum` int NOT NULL AUTO_INCREMENT,
  `DocEntry` int NOT NULL,
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` decimal(6,0) DEFAULT NULL,
  `LineStatus` tinyint(1) NOT NULL DEFAULT '0',
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Dscription` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` decimal(19,6) DEFAULT NULL,
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Text` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DUsage` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PQTReqQty` decimal(19,6) DEFAULT NULL,
  `PQTReqDate` date DEFAULT NULL,
  `PcDocType` decimal(6,0) DEFAULT NULL,
  `PcQuantity` decimal(19,6) DEFAULT NULL,
  `LinManClsd` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatGrpSrc` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`LineNum`),
  KEY `DocEntry` (`DocEntry`),
  CONSTRAINT `RPD1_ibfk_1` FOREIGN KEY (`DocEntry`) REFERENCES `ORPD` (`DocEntry`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=60 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `TECHNICIAN_PROFILE`
--

DROP TABLE IF EXISTS `TECHNICIAN_PROFILE`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `TECHNICIAN_PROFILE` (
  `TECH_ID` int NOT NULL AUTO_INCREMENT,
  `USER_ID` int DEFAULT NULL,
  `FIRST_NAME` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `LAST_NAME` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `DESIGNATION` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Junior',
  `IS_ACTIVE` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Y',
  PRIMARY KEY (`TECH_ID`),
  KEY `fk_tech_profile_user` (`USER_ID`),
  CONSTRAINT `fk_tech_profile_user` FOREIGN KEY (`USER_ID`) REFERENCES `USER` (`USER_ID`) ON DELETE SET NULL ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=70 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `TECHNICIAN_SKILL`
--

DROP TABLE IF EXISTS `TECHNICIAN_SKILL`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `TECHNICIAN_SKILL` (
  `ID` int NOT NULL AUTO_INCREMENT,
  `TECH_ID` int NOT NULL COMMENT 'Links to Master Technician Profile',
  `EQUIPMENT_TYPE` varchar(30) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL COMMENT 'VRF, AHU, CHW_FCU, SPLIT_TYPE, CHILLER, NONE',
  `SKILL_TYPE` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL COMMENT 'INSTALLATION, PM, TROUBLESHOOTING, DUCTMAN, PIPE_FITTER, ELECTRICIAN, WELDER',
  `MASTERY_LEVEL` enum('Novice','Intermediate','Expert') CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT 'Novice',
  `VERIFIED_AT` datetime DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`ID`),
  UNIQUE KEY `uq_tech_skill_matrix` (`TECH_ID`,`EQUIPMENT_TYPE`,`SKILL_TYPE`),
  KEY `idx_tech_id` (`TECH_ID`),
  CONSTRAINT `fk_skills_profile` FOREIGN KEY (`TECH_ID`) REFERENCES `TECHNICIAN_PROFILE` (`TECH_ID`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=273 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `TOOL_EQUIPMENT`
--

DROP TABLE IF EXISTS `TOOL_EQUIPMENT`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `TOOL_EQUIPMENT` (
  `TOOL_ID` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `EQUIPMENT_TYPE` varchar(15) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL COMMENT 'VRF, AHU, CHWFCU, ST, CHILLER',
  PRIMARY KEY (`TOOL_ID`,`EQUIPMENT_TYPE`),
  CONSTRAINT `TOOL_EQUIPMENT_ibfk_1` FOREIGN KEY (`TOOL_ID`) REFERENCES `TOOL_MASTER` (`TOOL_ID`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `TOOL_ITEMS`
--

DROP TABLE IF EXISTS `TOOL_ITEMS`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `TOOL_ITEMS` (
  `ASSET_ID` int NOT NULL AUTO_INCREMENT COMMENT 'Unique tracker identifier',
  `TOOL_ID` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL COMMENT 'References ItemCode from TOOL_MASTER',
  `SERIAL_NO` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Optional: Only for high-value gear (Fluke, Megger, etc.)',
  `INTERNAL_TAG` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL COMMENT 'Mandatory: Your warehouse barcode label (e.g., BOX-001, PM-05)',
  `STATUS` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Available' COMMENT 'Available, In-Use, Broken',
  PRIMARY KEY (`ASSET_ID`),
  UNIQUE KEY `idx_asset_tag` (`INTERNAL_TAG`),
  KEY `TOOL_ID` (`TOOL_ID`),
  CONSTRAINT `TOOL_ITEMS_ibfk_1` FOREIGN KEY (`TOOL_ID`) REFERENCES `TOOL_MASTER` (`TOOL_ID`) ON DELETE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=65 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `TOOL_MASTER`
--

DROP TABLE IF EXISTS `TOOL_MASTER`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `TOOL_MASTER` (
  `TOOL_ID` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL COMMENT 'Contains ItemCode like TLSHNDT001228',
  `TOOL_NAME` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `CATEGORY` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IS_ACTIVE` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Y',
  PRIMARY KEY (`TOOL_ID`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `TOOL_SERVICES`
--

DROP TABLE IF EXISTS `TOOL_SERVICES`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `TOOL_SERVICES` (
  `TOOL_ID` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `SERVICE_TYPE` varchar(10) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL COMMENT 'TS = Trouble-Shoot/Repair/Warranty/Survey, PM = Preventive Maintenance, INS = Installation/Commissioning',
  PRIMARY KEY (`TOOL_ID`,`SERVICE_TYPE`),
  CONSTRAINT `TOOL_SERVICES_ibfk_1` FOREIGN KEY (`TOOL_ID`) REFERENCES `TOOL_MASTER` (`TOOL_ID`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `TOOL_SERVICES_2`
--

DROP TABLE IF EXISTS `TOOL_SERVICES_2`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `TOOL_SERVICES_2` (
  `TOOL_ID` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `SERVICE_TYPE_2` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL COMMENT 'Installation, Preventive Maintenance, Trouble Shoot',
  PRIMARY KEY (`TOOL_ID`,`SERVICE_TYPE_2`),
  CONSTRAINT `TOOL_SERVICES_2_ibfk_1` FOREIGN KEY (`TOOL_ID`) REFERENCES `TOOL_MASTER` (`TOOL_ID`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `TRANS`
--

DROP TABLE IF EXISTS `TRANS`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `TRANS` (
  `TransTypeID` int NOT NULL AUTO_INCREMENT,
  `TransName` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  PRIMARY KEY (`TransTypeID`)
) ENGINE=InnoDB AUTO_INCREMENT=25 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `USER`
--

DROP TABLE IF EXISTS `USER`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `USER` (
  `USER_ID` int NOT NULL AUTO_INCREMENT,
  `FNAME` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `LNAME` varchar(60) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `JOBTITLE` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci DEFAULT NULL,
  `DEPTID` int NOT NULL,
  `USERNAME` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `PASSWORD` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `PASSWORD_TXT` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `ROLE` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `MANAGERID` int NOT NULL,
  `TENANT_ID` int NOT NULL,
  `CurrentLat` decimal(11,8) DEFAULT NULL,
  `CurrentLong` decimal(11,8) DEFAULT NULL,
  `LastLocationUpdate` datetime DEFAULT NULL,
  PRIMARY KEY (`USER_ID`),
  KEY `DEPTID` (`DEPTID`),
  CONSTRAINT `USER_ibfk_1` FOREIGN KEY (`DEPTID`) REFERENCES `DEPARTMENT` (`DEPT_ID`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=82 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `VEHICLE_MASTER`
--

DROP TABLE IF EXISTS `VEHICLE_MASTER`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `VEHICLE_MASTER` (
  `VEHICLE_ID` int NOT NULL AUTO_INCREMENT,
  `MODEL` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `PLATE_NO` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `IS_ACTIVE` char(1) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT 'Y',
  PRIMARY KEY (`VEHICLE_ID`),
  UNIQUE KEY `idx_plate_no` (`PLATE_NO`)
) ENGINE=InnoDB AUTO_INCREMENT=14 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `Valuation`
--

DROP TABLE IF EXISTS `Valuation`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `Valuation` (
  `ValType` int NOT NULL AUTO_INCREMENT,
  `ValName` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  PRIMARY KEY (`ValType`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `WDD1`
--

DROP TABLE IF EXISTS `WDD1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `WDD1` (
  `Wdd1ID` int NOT NULL AUTO_INCREMENT,
  `WddCode` int NOT NULL,
  `StepCode` int NOT NULL,
  `UserID` int DEFAULT NULL,
  `Status` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci NOT NULL,
  `Remarks` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `UserSign` int DEFAULT NULL,
  `CreateDate` date NOT NULL,
  `CreateTime` time NOT NULL,
  `UpdateDate` date DEFAULT NULL,
  `UpdateTime` time DEFAULT NULL,
  PRIMARY KEY (`Wdd1ID`),
  KEY `StepCode` (`StepCode`),
  KEY `WddCode` (`WddCode`),
  KEY `UserID` (`UserID`),
  KEY `Status` (`Status`),
  CONSTRAINT `WDD1_ibfk_2` FOREIGN KEY (`WddCode`) REFERENCES `OWDD` (`WddCode`) ON DELETE RESTRICT ON UPDATE CASCADE,
  CONSTRAINT `WDD1_ibfk_3` FOREIGN KEY (`Status`) REFERENCES `OCLA` (`name`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=8826 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
/*!50003 CREATE*/ /*!50017 DEFINER=`ultimau5_jvmacuh`@`%`*/ /*!50003 TRIGGER `trg_WDD1_Decision_Engine` AFTER UPDATE ON `WDD1` FOR EACH ROW BEGIN
    -- Only run logic if the status actually changed to prevent recursion
    IF NEW.Status <> OLD.Status THEN
        
        -- Logic for Approval (Y)
        IF NEW.Status = 'Y' THEN
            -- We call a modified version of the approval logic 
            -- that DOES NOT update WDD1 itself
            CALL sp_SyncHeaderAndDoc(NEW.WddCode);
            
        -- Logic for Cancellation (N)
        ELSEIF NEW.Status = 'N' THEN
            CALL sp_SyncHeaderAndDoc_Force(NEW.WddCode, 'N');
            
        -- Logic for Re-opening (W)
        ELSEIF NEW.Status = 'W' THEN
            CALL sp_SyncHeaderAndDoc_Force(NEW.WddCode, 'W');
            
		 ELSEIF NEW.Status = 'R' THEN
            CALL sp_SyncHeaderAndDoc_Force(NEW.WddCode, 'R');
        END IF;
        
    END IF;
END */;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;

--
-- Table structure for table `WST1`
--

DROP TABLE IF EXISTS `WST1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `WST1` (
  `wst1Id` int NOT NULL AUTO_INCREMENT,
  `WstCode` int NOT NULL,
  `UserID` int NOT NULL,
  PRIMARY KEY (`wst1Id`),
  KEY `WstCode` (`WstCode`),
  KEY `UserID` (`UserID`),
  CONSTRAINT `WST1_ibfk_1` FOREIGN KEY (`WstCode`) REFERENCES `OWST` (`WstCode`) ON DELETE RESTRICT ON UPDATE RESTRICT,
  CONSTRAINT `WST1_ibfk_2` FOREIGN KEY (`UserID`) REFERENCES `USER` (`USER_ID`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=38 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `WTM1`
--

DROP TABLE IF EXISTS `WTM1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `WTM1` (
  `Wtm1Id` int NOT NULL AUTO_INCREMENT,
  `WtmCode` int NOT NULL,
  `UserID` int DEFAULT NULL,
  PRIMARY KEY (`Wtm1Id`),
  KEY `WtmCode` (`WtmCode`),
  KEY `UserID` (`UserID`),
  CONSTRAINT `WTM1_ibfk_1` FOREIGN KEY (`WtmCode`) REFERENCES `OWTM` (`WtmCode`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `WTM1_ibfk_2` FOREIGN KEY (`UserID`) REFERENCES `USER` (`USER_ID`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=162 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `WTM2`
--

DROP TABLE IF EXISTS `WTM2`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `WTM2` (
  `Wtm2Id` int NOT NULL AUTO_INCREMENT,
  `WtmCode` int NOT NULL,
  `WstCode` int NOT NULL,
  `SortId` int NOT NULL,
  `Remarks` char(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SortOrder` int NOT NULL DEFAULT '0',
  PRIMARY KEY (`Wtm2Id`),
  KEY `WtmCode` (`WtmCode`,`WstCode`),
  KEY `WstCode` (`WstCode`),
  CONSTRAINT `WTM2_ibfk_1` FOREIGN KEY (`WtmCode`) REFERENCES `OWTM` (`WtmCode`) ON DELETE CASCADE ON UPDATE CASCADE,
  CONSTRAINT `WTM2_ibfk_2` FOREIGN KEY (`WstCode`) REFERENCES `OWST` (`WstCode`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=84 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `WTM3`
--

DROP TABLE IF EXISTS `WTM3`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `WTM3` (
  `Wtm3Id` int NOT NULL AUTO_INCREMENT,
  `WtmCode` int NOT NULL,
  `UserSign` int NOT NULL,
  `TransType` int NOT NULL,
  PRIMARY KEY (`Wtm3Id`),
  KEY `WtmCode` (`WtmCode`),
  KEY `TransType` (`TransType`),
  CONSTRAINT `WTM3_ibfk_1` FOREIGN KEY (`TransType`) REFERENCES `TRANS` (`TransTypeID`) ON DELETE RESTRICT ON UPDATE CASCADE,
  CONSTRAINT `WTM3_ibfk_2` FOREIGN KEY (`WtmCode`) REFERENCES `OWTM` (`WtmCode`) ON DELETE RESTRICT ON UPDATE CASCADE
) ENGINE=InnoDB AUTO_INCREMENT=105 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `WTM4`
--

DROP TABLE IF EXISTS `WTM4`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `WTM4` (
  `WTM4Id` int NOT NULL AUTO_INCREMENT,
  `WtmCode` int NOT NULL,
  `CondId` int NOT NULL,
  `opCode` int NOT NULL,
  `opValue` varchar(90) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  PRIMARY KEY (`WTM4Id`)
) ENGINE=InnoDB AUTO_INCREMENT=33 DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `WTM5`
--

DROP TABLE IF EXISTS `WTM5`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `WTM5` (
  `WtmCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'Code',
  `QueryId` int DEFAULT NULL COMMENT 'User Query Id'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `WTM_CONDITIONS`
--

DROP TABLE IF EXISTS `WTM_CONDITIONS`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `WTM_CONDITIONS` (
  `CondId` int NOT NULL,
  `CondName` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `DefaultRatio` varchar(5) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `IsActive` bit(1) DEFAULT b'1',
  PRIMARY KEY (`CondId`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `WTR1`
--

DROP TABLE IF EXISTS `WTR1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `WTR1` (
  `DocEntry` int NOT NULL,
  `LineNum` int NOT NULL,
  `ItemCode` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Dscription` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `FromWhsCod` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `WhsCode` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `Project` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  `OcrCode` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci DEFAULT NULL,
  PRIMARY KEY (`DocEntry`,`LineNum`),
  CONSTRAINT `FK_OWTR_WTR1` FOREIGN KEY (`DocEntry`) REFERENCES `OWTR` (`DocEntry`) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `app_communications_log`
--

DROP TABLE IF EXISTS `app_communications_log`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `app_communications_log` (
  `id` int NOT NULL AUTO_INCREMENT,
  `module_type` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL COMMENT 'e.g., PO, SRID, INV, CUSTOMER_PORTAL',
  `transaction_id` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'The primary key of the transaction (e.g., WddCode, SRID, DocEntry)',
  `card_code` varchar(50) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT 'The Vendor or Client Code (e.g., CardCode)',
  `user_id` int NOT NULL COMMENT 'Links to USER table identifying the sender',
  `comment` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  `is_read` tinyint(1) DEFAULT '0',
  PRIMARY KEY (`id`),
  KEY `idx_module_tx` (`module_type`,`transaction_id`),
  KEY `idx_card_code` (`card_code`),
  KEY `idx_created` (`created_at` DESC)
) ENGINE=InnoDB AUTO_INCREMENT=166 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Temporary view structure for view `approval_mapping`
--

DROP TABLE IF EXISTS `approval_mapping`;
/*!50001 DROP VIEW IF EXISTS `approval_mapping`*/;
SET @saved_cs_client     = @@character_set_client;
/*!50503 SET character_set_client = utf8mb4 */;
/*!50001 CREATE VIEW `approval_mapping` AS SELECT 
 1 AS `FNAME`,
 1 AS `LNAME`,
 1 AS `WstCode`,
 1 AS `Name`,
 1 AS `Remarks`,
 1 AS `MaxReqr`*/;
SET character_set_client = @saved_cs_client;

--
-- Temporary view structure for view `bin_stock`
--

DROP TABLE IF EXISTS `bin_stock`;
/*!50001 DROP VIEW IF EXISTS `bin_stock`*/;
SET @saved_cs_client     = @@character_set_client;
/*!50503 SET character_set_client = utf8mb4 */;
/*!50001 CREATE VIEW `bin_stock` AS SELECT 
 1 AS `ItemCode`,
 1 AS `ItemName`,
 1 AS `WhsCode`,
 1 AS `WhsName`,
 1 AS `BinAbs`,
 1 AS `BinCode`,
 1 AS `OnHand`*/;
SET character_set_client = @saved_cs_client;

--
-- Table structure for table `charttype`
--

DROP TABLE IF EXISTS `charttype`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `charttype` (
  `ActType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci NOT NULL,
  `TypeName` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3 COLLATE=utf8mb3_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Temporary view structure for view `inventory_ledger`
--

DROP TABLE IF EXISTS `inventory_ledger`;
/*!50001 DROP VIEW IF EXISTS `inventory_ledger`*/;
SET @saved_cs_client     = @@character_set_client;
/*!50503 SET character_set_client = utf8mb4 */;
/*!50001 CREATE VIEW `inventory_ledger` AS SELECT 
 1 AS `ItemCode`,
 1 AS `WhsCode`,
 1 AS `DocDate`,
 1 AS `TransType`,
 1 AS `DocEntry`,
 1 AS `DocNum`,
 1 AS `LineIdentifier`,
 1 AS `InQty`,
 1 AS `OutQty`*/;
SET character_set_client = @saved_cs_client;

--
-- Temporary view structure for view `item_master`
--

DROP TABLE IF EXISTS `item_master`;
/*!50001 DROP VIEW IF EXISTS `item_master`*/;
SET @saved_cs_client     = @@character_set_client;
/*!50503 SET character_set_client = utf8mb4 */;
/*!50001 CREATE VIEW `item_master` AS SELECT 
 1 AS `ItemCode`,
 1 AS `ItemName`,
 1 AS `ItmsGrpCod`,
 1 AS `InvntItem`,
 1 AS `SalUnitMsr`,
 1 AS `BuyUnitMsr`,
 1 AS `ManSerNum`,
 1 AS `ManBtchNum`,
 1 AS `Spec`*/;
SET character_set_client = @saved_cs_client;

--
-- Temporary view structure for view `item_stock`
--

DROP TABLE IF EXISTS `item_stock`;
/*!50001 DROP VIEW IF EXISTS `item_stock`*/;
SET @saved_cs_client     = @@character_set_client;
/*!50503 SET character_set_client = utf8mb4 */;
/*!50001 CREATE VIEW `item_stock` AS SELECT 
 1 AS `ItemCode`,
 1 AS `ItemName`,
 1 AS `ItmsGrpCod`,
 1 AS `invntryUom`,
 1 AS `Spec`,
 1 AS `WhsCode`,
 1 AS `WhsName`,
 1 AS `OnHand`,
 1 AS `OnPO`,
 1 AS `OnSO`,
 1 AS `Available`*/;
SET character_set_client = @saved_cs_client;

--
-- Table structure for table `oitm__52_`
--

DROP TABLE IF EXISTS `oitm__52_`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `oitm__52_` (
  `COL 1` varchar(15) DEFAULT NULL,
  `COL 2` varchar(19) DEFAULT NULL,
  `COL 3` varchar(124) DEFAULT NULL,
  `COL 4` varchar(124) DEFAULT NULL,
  `COL 5` varchar(2) DEFAULT NULL,
  `COL 6` varchar(1) DEFAULT NULL,
  `COL 7` varchar(3) DEFAULT NULL,
  `COL 8` varchar(10) DEFAULT NULL,
  `COL 9` varchar(10) DEFAULT NULL,
  `COL 10` varchar(1) DEFAULT NULL,
  `COL 11` varchar(1) DEFAULT NULL,
  `COL 12` varchar(1) DEFAULT NULL,
  `COL 13` varchar(1) DEFAULT NULL,
  `COL 14` varchar(1) DEFAULT NULL,
  `COL 15` varchar(1) DEFAULT NULL,
  `COL 16` varchar(10) DEFAULT NULL,
  `COL 17` varchar(10) DEFAULT NULL,
  `COL 18` varchar(1) DEFAULT NULL,
  `COL 19` varchar(7) DEFAULT NULL,
  `COL 20` varchar(10) DEFAULT NULL,
  `COL 21` varchar(10) DEFAULT NULL,
  `COL 22` varchar(7) DEFAULT NULL,
  `COL 23` varchar(10) DEFAULT NULL,
  `COL 24` varchar(10) DEFAULT NULL,
  `COL 25` varchar(10) DEFAULT NULL,
  `COL 26` varchar(10) DEFAULT NULL,
  `COL 27` varchar(10) DEFAULT NULL,
  `COL 28` varchar(10) DEFAULT NULL,
  `COL 29` varchar(10) DEFAULT NULL,
  `COL 30` varchar(10) DEFAULT NULL,
  `COL 31` varchar(10) DEFAULT NULL,
  `COL 32` varchar(10) DEFAULT NULL,
  `COL 33` varchar(10) DEFAULT NULL,
  `COL 34` varchar(10) DEFAULT NULL,
  `COL 35` varchar(10) DEFAULT NULL,
  `COL 36` varchar(7) DEFAULT NULL,
  `COL 37` varchar(10) DEFAULT NULL,
  `COL 38` varchar(10) DEFAULT NULL,
  `COL 39` varchar(10) DEFAULT NULL,
  `COL 40` varchar(10) DEFAULT NULL,
  `COL 41` varchar(10) DEFAULT NULL,
  `COL 42` varchar(10) DEFAULT NULL,
  `COL 43` varchar(10) DEFAULT NULL,
  `COL 44` varchar(10) DEFAULT NULL,
  `COL 45` varchar(10) DEFAULT NULL,
  `COL 46` varchar(10) DEFAULT NULL,
  `COL 47` varchar(10) DEFAULT NULL,
  `COL 48` varchar(10) DEFAULT NULL,
  `COL 49` varchar(10) DEFAULT NULL,
  `COL 50` varchar(10) DEFAULT NULL,
  `COL 51` varchar(10) DEFAULT NULL,
  `COL 52` varchar(10) DEFAULT NULL,
  `COL 53` varchar(10) DEFAULT NULL,
  `COL 54` varchar(10) DEFAULT NULL,
  `COL 55` varchar(6) DEFAULT NULL,
  `COL 56` varchar(10) DEFAULT NULL,
  `COL 57` varchar(10) DEFAULT NULL,
  `COL 58` varchar(10) DEFAULT NULL,
  `COL 59` varchar(9) DEFAULT NULL,
  `COL 60` varchar(3) DEFAULT NULL,
  `COL 61` varchar(1) DEFAULT NULL,
  `COL 62` varchar(10) DEFAULT NULL,
  `COL 63` varchar(1) DEFAULT NULL,
  `COL 64` varchar(10) DEFAULT NULL,
  `COL 65` varchar(10) DEFAULT NULL,
  `COL 66` varchar(10) DEFAULT NULL,
  `COL 67` varchar(10) DEFAULT NULL,
  `COL 68` varchar(10) DEFAULT NULL,
  `COL 69` varchar(10) DEFAULT NULL,
  `COL 70` varchar(10) DEFAULT NULL,
  `COL 71` varchar(10) DEFAULT NULL,
  `COL 72` varchar(10) DEFAULT NULL,
  `COL 73` varchar(10) DEFAULT NULL,
  `COL 74` varchar(10) DEFAULT NULL,
  `COL 75` varchar(10) DEFAULT NULL,
  `COL 76` varchar(10) DEFAULT NULL,
  `COL 77` varchar(10) DEFAULT NULL,
  `COL 78` varchar(10) DEFAULT NULL,
  `COL 79` varchar(10) DEFAULT NULL,
  `COL 80` varchar(10) DEFAULT NULL,
  `COL 81` varchar(10) DEFAULT NULL,
  `COL 82` varchar(10) DEFAULT NULL,
  `COL 83` varchar(10) DEFAULT NULL,
  `COL 84` varchar(10) DEFAULT NULL,
  `COL 85` varchar(10) DEFAULT NULL,
  `COL 86` varchar(10) DEFAULT NULL,
  `COL 87` varchar(10) DEFAULT NULL,
  `COL 88` varchar(10) DEFAULT NULL,
  `COL 89` varchar(10) DEFAULT NULL,
  `COL 90` varchar(10) DEFAULT NULL,
  `COL 91` varchar(10) DEFAULT NULL,
  `COL 92` varchar(10) DEFAULT NULL,
  `COL 93` varchar(10) DEFAULT NULL,
  `COL 94` varchar(10) DEFAULT NULL,
  `COL 95` varchar(10) DEFAULT NULL,
  `COL 96` varchar(10) DEFAULT NULL,
  `COL 97` varchar(10) DEFAULT NULL,
  `COL 98` varchar(10) DEFAULT NULL,
  `COL 99` varchar(10) DEFAULT NULL,
  `COL 100` varchar(10) DEFAULT NULL,
  `COL 101` varchar(10) DEFAULT NULL,
  `COL 102` varchar(10) DEFAULT NULL,
  `COL 103` varchar(10) DEFAULT NULL,
  `COL 104` varchar(10) DEFAULT NULL,
  `COL 105` varchar(10) DEFAULT NULL,
  `COL 106` varchar(10) DEFAULT NULL,
  `COL 107` varchar(10) DEFAULT NULL,
  `COL 108` varchar(10) DEFAULT NULL,
  `COL 109` varchar(10) DEFAULT NULL,
  `COL 110` varchar(10) DEFAULT NULL,
  `COL 111` varchar(10) DEFAULT NULL,
  `COL 112` varchar(10) DEFAULT NULL,
  `COL 113` varchar(10) DEFAULT NULL,
  `COL 114` varchar(10) DEFAULT NULL,
  `COL 115` varchar(10) DEFAULT NULL,
  `COL 116` varchar(10) DEFAULT NULL,
  `COL 117` varchar(10) DEFAULT NULL,
  `COL 118` varchar(10) DEFAULT NULL,
  `COL 119` varchar(10) DEFAULT NULL,
  `COL 120` varchar(10) DEFAULT NULL,
  `COL 121` varchar(10) DEFAULT NULL,
  `COL 122` varchar(10) DEFAULT NULL,
  `COL 123` varchar(10) DEFAULT NULL,
  `COL 124` varchar(10) DEFAULT NULL,
  `COL 125` varchar(10) DEFAULT NULL,
  `COL 126` varchar(10) DEFAULT NULL,
  `COL 127` varchar(10) DEFAULT NULL,
  `COL 128` varchar(10) DEFAULT NULL,
  `COL 129` varchar(10) DEFAULT NULL,
  `COL 130` varchar(10) DEFAULT NULL,
  `COL 131` varchar(10) DEFAULT NULL,
  `COL 132` varchar(10) DEFAULT NULL,
  `COL 133` varchar(10) DEFAULT NULL,
  `COL 134` varchar(10) DEFAULT NULL,
  `COL 135` varchar(10) DEFAULT NULL,
  `COL 136` varchar(10) DEFAULT NULL,
  `COL 137` varchar(10) DEFAULT NULL,
  `COL 138` varchar(10) DEFAULT NULL,
  `COL 139` varchar(10) DEFAULT NULL,
  `COL 140` varchar(10) DEFAULT NULL,
  `COL 141` varchar(10) DEFAULT NULL,
  `COL 142` varchar(10) DEFAULT NULL,
  `COL 143` varchar(10) DEFAULT NULL,
  `COL 144` varchar(10) DEFAULT NULL,
  `COL 145` varchar(10) DEFAULT NULL,
  `COL 146` varchar(10) DEFAULT NULL,
  `COL 147` varchar(10) DEFAULT NULL,
  `COL 148` varchar(10) DEFAULT NULL,
  `COL 149` varchar(10) DEFAULT NULL,
  `COL 150` varchar(10) DEFAULT NULL,
  `COL 151` varchar(10) DEFAULT NULL,
  `COL 152` varchar(10) DEFAULT NULL,
  `COL 153` varchar(10) DEFAULT NULL,
  `COL 154` varchar(10) DEFAULT NULL,
  `COL 155` varchar(10) DEFAULT NULL,
  `COL 156` varchar(10) DEFAULT NULL,
  `COL 157` varchar(10) DEFAULT NULL,
  `COL 158` varchar(10) DEFAULT NULL,
  `COL 159` varchar(10) DEFAULT NULL,
  `COL 160` varchar(10) DEFAULT NULL,
  `COL 161` varchar(10) DEFAULT NULL,
  `COL 162` varchar(10) DEFAULT NULL,
  `COL 163` varchar(10) DEFAULT NULL,
  `COL 164` varchar(10) DEFAULT NULL,
  `COL 165` varchar(10) DEFAULT NULL,
  `COL 166` varchar(10) DEFAULT NULL,
  `COL 167` varchar(10) DEFAULT NULL,
  `COL 168` varchar(10) DEFAULT NULL,
  `COL 169` varchar(10) DEFAULT NULL,
  `COL 170` varchar(10) DEFAULT NULL,
  `COL 171` varchar(10) DEFAULT NULL,
  `COL 172` varchar(10) DEFAULT NULL,
  `COL 173` varchar(10) DEFAULT NULL,
  `COL 174` varchar(10) DEFAULT NULL,
  `COL 175` varchar(10) DEFAULT NULL,
  `COL 176` varchar(10) DEFAULT NULL,
  `COL 177` varchar(10) DEFAULT NULL,
  `COL 178` varchar(10) DEFAULT NULL,
  `COL 179` varchar(10) DEFAULT NULL,
  `COL 180` varchar(10) DEFAULT NULL,
  `COL 181` varchar(4) DEFAULT NULL,
  `COL 182` varchar(10) DEFAULT NULL,
  `COL 183` varchar(2) DEFAULT NULL,
  `COL 184` varchar(10) DEFAULT NULL,
  `COL 185` varchar(10) DEFAULT NULL,
  `COL 186` varchar(10) DEFAULT NULL,
  `COL 187` varchar(10) DEFAULT NULL,
  `COL 188` varchar(10) DEFAULT NULL,
  `COL 189` varchar(1) DEFAULT NULL,
  `COL 190` varchar(10) DEFAULT NULL,
  `COL 191` varchar(10) DEFAULT NULL,
  `COL 192` varchar(10) DEFAULT NULL,
  `COL 193` varchar(10) DEFAULT NULL,
  `COL 194` varchar(10) DEFAULT NULL,
  `COL 195` varchar(10) DEFAULT NULL,
  `COL 196` varchar(10) DEFAULT NULL,
  `COL 197` varchar(10) DEFAULT NULL,
  `COL 198` varchar(10) DEFAULT NULL,
  `COL 199` varchar(7) DEFAULT NULL,
  `COL 200` varchar(10) DEFAULT NULL,
  `COL 201` varchar(10) DEFAULT NULL,
  `COL 202` varchar(10) DEFAULT NULL,
  `COL 203` varchar(10) DEFAULT NULL,
  `COL 204` varchar(10) DEFAULT NULL,
  `COL 205` varchar(10) DEFAULT NULL,
  `COL 206` varchar(10) DEFAULT NULL,
  `COL 207` varchar(10) DEFAULT NULL,
  `COL 208` varchar(10) DEFAULT NULL,
  `COL 209` varchar(10) DEFAULT NULL,
  `COL 210` varchar(10) DEFAULT NULL,
  `COL 211` varchar(10) DEFAULT NULL,
  `COL 212` varchar(10) DEFAULT NULL,
  `COL 213` varchar(10) DEFAULT NULL,
  `COL 214` varchar(10) DEFAULT NULL,
  `COL 215` varchar(10) DEFAULT NULL,
  `COL 216` varchar(10) DEFAULT NULL,
  `COL 217` varchar(10) DEFAULT NULL,
  `COL 218` varchar(10) DEFAULT NULL,
  `COL 219` varchar(10) DEFAULT NULL,
  `COL 220` varchar(10) DEFAULT NULL,
  `COL 221` varchar(10) DEFAULT NULL,
  `COL 222` varchar(1) DEFAULT NULL,
  `COL 223` varchar(10) DEFAULT NULL,
  `COL 224` varchar(7) DEFAULT NULL,
  `COL 225` varchar(10) DEFAULT NULL,
  `COL 226` varchar(10) DEFAULT NULL,
  `COL 227` varchar(10) DEFAULT NULL,
  `COL 228` varchar(10) DEFAULT NULL,
  `COL 229` varchar(10) DEFAULT NULL,
  `COL 230` varchar(10) DEFAULT NULL,
  `COL 231` varchar(10) DEFAULT NULL,
  `COL 232` varchar(10) DEFAULT NULL,
  `COL 233` varchar(10) DEFAULT NULL,
  `COL 234` varchar(10) DEFAULT NULL,
  `COL 235` varchar(10) DEFAULT NULL,
  `COL 236` varchar(10) DEFAULT NULL,
  `COL 237` varchar(10) DEFAULT NULL,
  `COL 238` varchar(10) DEFAULT NULL,
  `COL 239` varchar(10) DEFAULT NULL,
  `COL 240` varchar(10) DEFAULT NULL,
  `COL 241` varchar(10) DEFAULT NULL,
  `COL 242` varchar(10) DEFAULT NULL,
  `COL 243` varchar(10) DEFAULT NULL,
  `COL 244` varchar(10) DEFAULT NULL,
  `COL 245` varchar(10) DEFAULT NULL,
  `COL 246` varchar(10) DEFAULT NULL,
  `COL 247` varchar(10) DEFAULT NULL,
  `COL 248` varchar(10) DEFAULT NULL,
  `COL 249` varchar(10) DEFAULT NULL,
  `COL 250` varchar(12) DEFAULT NULL,
  `COL 251` varchar(10) DEFAULT NULL,
  `COL 252` varchar(10) DEFAULT NULL,
  `COL 253` varchar(10) DEFAULT NULL,
  `COL 254` varchar(10) DEFAULT NULL,
  `COL 255` varchar(10) DEFAULT NULL,
  `COL 256` varchar(10) DEFAULT NULL,
  `COL 257` varchar(10) DEFAULT NULL,
  `COL 258` varchar(10) DEFAULT NULL,
  `COL 259` varchar(10) DEFAULT NULL,
  `COL 260` varchar(10) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `po_approval_comments`
--

DROP TABLE IF EXISTS `po_approval_comments`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `po_approval_comments` (
  `id` int NOT NULL AUTO_INCREMENT,
  `po_doc_entry` int NOT NULL,
  `wdd_code` int NOT NULL,
  `step_code` int DEFAULT NULL COMMENT 'Tracks specific approval step if submitted by an approver',
  `author_id` int DEFAULT NULL,
  `author_name` varchar(100) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `comment_text` text CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci NOT NULL,
  `wdd_status_at_time` varchar(20) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`),
  KEY `idx_po_doc_entry` (`po_doc_entry`),
  KEY `idx_wdd_code` (`wdd_code`)
) ENGINE=InnoDB AUTO_INCREMENT=86 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `tempPCH`
--

DROP TABLE IF EXISTS `tempPCH`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `tempPCH` (
  `DocID` int DEFAULT NULL,
  `DocEntry` int DEFAULT '0',
  `TargetType` decimal(6,0) DEFAULT NULL,
  `TrgetEntry` decimal(6,0) DEFAULT NULL,
  `BaseRef` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseType` decimal(6,0) DEFAULT NULL,
  `BaseEntry` decimal(6,0) DEFAULT NULL,
  `BaseLine` decimal(6,0) DEFAULT NULL,
  `LineStatus` tinyint(1) NOT NULL DEFAULT '0',
  `ItemCode` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Dscription` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Quantity` decimal(19,6) DEFAULT NULL,
  `ShipDate` date DEFAULT NULL,
  `OpenQty` decimal(19,6) DEFAULT NULL,
  `Price` decimal(19,6) DEFAULT NULL,
  `Currency` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Rate` decimal(19,6) DEFAULT NULL,
  `DiscPrcnt` decimal(19,6) DEFAULT NULL,
  `LineTotal` decimal(19,6) DEFAULT NULL,
  `TotalFrgn` decimal(19,6) DEFAULT NULL,
  `OpenSum` decimal(19,6) DEFAULT NULL,
  `OpenSumFC` decimal(19,6) DEFAULT NULL,
  `VendorNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SerialNum` varchar(17) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WhsCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SlpCode` decimal(6,0) DEFAULT NULL,
  `Commission` decimal(19,6) DEFAULT NULL,
  `TreeType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AcctCode` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBuyPr` decimal(19,6) DEFAULT NULL,
  `PriceBefDi` decimal(19,6) DEFAULT NULL,
  `DocDate` date DEFAULT NULL,
  `Flags` decimal(6,0) DEFAULT NULL,
  `OpenCreQty` decimal(19,6) DEFAULT NULL,
  `UseBaseUn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SubCatNum` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseCard` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TotalSumSy` decimal(19,6) DEFAULT NULL,
  `OpenSumSys` decimal(19,6) DEFAULT NULL,
  `InvntSttus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Project` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CodeBars` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatPrcnt` decimal(19,6) DEFAULT NULL,
  `VatGroup` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PriceAfVAT` decimal(19,6) DEFAULT NULL,
  `Height1` decimal(19,6) DEFAULT NULL,
  `Hght1Unit` decimal(6,0) DEFAULT NULL,
  `Height2` decimal(19,6) DEFAULT NULL,
  `Hght2Unit` decimal(6,0) DEFAULT NULL,
  `Width1` decimal(19,6) DEFAULT NULL,
  `Wdth1Unit` decimal(6,0) DEFAULT NULL,
  `Width2` decimal(19,6) DEFAULT NULL,
  `Wdth2Unit` decimal(6,0) DEFAULT NULL,
  `Length1` decimal(19,6) DEFAULT NULL,
  `Len1Unit` decimal(6,0) DEFAULT NULL,
  `length2` decimal(19,6) DEFAULT NULL,
  `Len2Unit` decimal(6,0) DEFAULT NULL,
  `Volume` decimal(19,6) DEFAULT NULL,
  `VolUnit` decimal(6,0) DEFAULT NULL,
  `Weight1` decimal(19,6) DEFAULT NULL,
  `Wght1Unit` decimal(6,0) DEFAULT NULL,
  `Weight2` decimal(19,6) DEFAULT NULL,
  `Wght2Unit` decimal(6,0) DEFAULT NULL,
  `Factor1` decimal(19,6) DEFAULT NULL,
  `Factor2` decimal(19,6) DEFAULT NULL,
  `Factor3` decimal(19,6) DEFAULT NULL,
  `Factor4` decimal(19,6) DEFAULT NULL,
  `PackQty` decimal(19,6) DEFAULT NULL,
  `UpdInvntry` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BaseDocNum` decimal(6,0) DEFAULT NULL,
  `BaseAtCard` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `SWW` varchar(16) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `VatSum` decimal(19,6) DEFAULT NULL,
  `VatSumFrgn` decimal(19,6) DEFAULT NULL,
  `VatSumSy` decimal(19,6) DEFAULT NULL,
  `FinncPriod` decimal(6,0) DEFAULT NULL,
  `ObjType` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LogInstanc` decimal(6,0) DEFAULT NULL,
  `BlockNum` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ImportLog` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DedVatSum` decimal(19,6) DEFAULT NULL,
  `DedVatSumF` decimal(19,6) DEFAULT NULL,
  `DedVatSumS` decimal(19,6) DEFAULT NULL,
  `IsAqcuistn` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DistribSum` decimal(19,6) DEFAULT NULL,
  `DstrbSumFC` decimal(19,6) DEFAULT NULL,
  `DstrbSumSC` decimal(19,6) DEFAULT NULL,
  `GrssProfit` decimal(19,6) DEFAULT NULL,
  `GrssProfSC` decimal(19,6) DEFAULT NULL,
  `GrssProfFC` decimal(19,6) DEFAULT NULL,
  `VisOrder` decimal(6,0) DEFAULT NULL,
  `INMPrice` decimal(19,6) DEFAULT NULL,
  `PoTrgNum` decimal(6,0) DEFAULT NULL,
  `PoTrgEntry` varchar(11) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DropShip` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PoLineNum` decimal(6,0) DEFAULT NULL,
  `Address` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxCode` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OrigItem` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `BackOrdr` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `FreeTxt` varchar(100) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickStatus` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `PickOty` decimal(19,6) DEFAULT NULL,
  `PickIdNo` decimal(6,0) DEFAULT NULL,
  `TrnsCode` decimal(6,0) DEFAULT NULL,
  `VatAppld` decimal(19,6) DEFAULT NULL,
  `VatAppldFC` decimal(19,6) DEFAULT NULL,
  `VatAppldSC` decimal(19,6) DEFAULT NULL,
  `BaseQty` decimal(19,6) DEFAULT NULL,
  `BaseOpnQty` decimal(19,6) DEFAULT NULL,
  `VatDscntPr` decimal(19,6) DEFAULT NULL,
  `WtLiable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DeferrTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `EquVatPer` decimal(19,6) DEFAULT NULL,
  `EquVatSum` decimal(19,6) DEFAULT NULL,
  `EquVatSumF` decimal(19,6) DEFAULT NULL,
  `EquVatSumS` decimal(19,6) DEFAULT NULL,
  `LineVat` decimal(19,6) DEFAULT NULL,
  `LineVatlF` decimal(19,6) DEFAULT NULL,
  `LineVatS` decimal(19,6) DEFAULT NULL,
  `unitMsr` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr` decimal(19,6) DEFAULT NULL,
  `CEECFlag` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ToStock` decimal(19,6) DEFAULT NULL,
  `ToDiff` decimal(19,6) DEFAULT NULL,
  `ExciseAmt` decimal(19,6) DEFAULT NULL,
  `TaxPerUnit` decimal(19,6) DEFAULT NULL,
  `TotInclTax` decimal(19,6) DEFAULT NULL,
  `CountryOrg` varchar(3) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckDstSum` decimal(19,6) DEFAULT NULL,
  `ReleasQtty` decimal(19,6) DEFAULT NULL,
  `LineType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TranType` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Text` varchar(255) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OwnerCode` decimal(6,0) DEFAULT NULL,
  `StockPrice` decimal(19,6) DEFAULT NULL,
  `ConsumeFCT` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LstByDsSum` decimal(19,6) DEFAULT NULL,
  `StckINMPr` decimal(19,6) DEFAULT NULL,
  `LstBINMPr` decimal(19,6) DEFAULT NULL,
  `StckDstFc` decimal(19,6) DEFAULT NULL,
  `StckDstSc` decimal(19,6) DEFAULT NULL,
  `LstByDsFc` decimal(19,6) DEFAULT NULL,
  `LstByDsSc` decimal(19,6) DEFAULT NULL,
  `StockSum` decimal(19,6) DEFAULT NULL,
  `StockSumFc` decimal(19,6) DEFAULT NULL,
  `StockSumSc` decimal(19,6) DEFAULT NULL,
  `StckSumApp` decimal(19,6) DEFAULT NULL,
  `StckAppFc` decimal(19,6) DEFAULT NULL,
  `StckAppSc` decimal(19,6) DEFAULT NULL,
  `ShipToCode` varchar(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ShipToDesc` varchar(254) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `StckAppD` decimal(19,6) DEFAULT NULL,
  `StckAppDFC` decimal(19,6) DEFAULT NULL,
  `StckAppDSC` decimal(19,6) DEFAULT NULL,
  `BasePrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GTotal` decimal(19,6) DEFAULT NULL,
  `GTotalFC` decimal(19,6) DEFAULT NULL,
  `GTotalSC` decimal(19,6) DEFAULT NULL,
  `DistribExp` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DescOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `DetailsOW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `GrossBase` decimal(6,0) DEFAULT NULL,
  `VatWoDpm` decimal(19,6) DEFAULT NULL,
  `VatWoDpmFc` decimal(19,6) DEFAULT NULL,
  `VatWoDpmSc` decimal(19,6) DEFAULT NULL,
  `CFOPCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTCode` varchar(6) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Usage1` decimal(6,0) DEFAULT NULL,
  `TaxOnly` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `WtCalced` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `QtyToShip` decimal(19,6) DEFAULT NULL,
  `DelivrdQty` decimal(19,6) DEFAULT NULL,
  `OrderedQty` decimal(19,6) DEFAULT NULL,
  `CogsOcrCod` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CiOppLineN` decimal(6,0) DEFAULT NULL,
  `CogsAcct` varchar(15) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ChgAsmBoMW` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ActDelDate` date DEFAULT NULL,
  `OcrCode2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `OcrCode5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `TaxDistSum` decimal(19,6) DEFAULT NULL,
  `TaxDistSFC` decimal(19,6) DEFAULT NULL,
  `TaxDistSSC` decimal(19,6) DEFAULT NULL,
  `PostTax` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `Excisable` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `AssblValue` decimal(19,6) DEFAULT NULL,
  `RG23APart1` decimal(6,0) DEFAULT NULL,
  `RG23APart2` decimal(6,0) DEFAULT NULL,
  `RG23CPart1` decimal(6,0) DEFAULT NULL,
  `RG23CPart2` decimal(6,0) DEFAULT NULL,
  `CogsOcrCo2` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo3` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo4` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CogsOcrCo5` varchar(8) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LnExcised` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `LocCode` decimal(6,0) DEFAULT NULL,
  `StockValue` decimal(19,6) DEFAULT NULL,
  `GPTtlBasPr` decimal(19,6) DEFAULT NULL,
  `unitMsr2` varchar(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `NumPerMsr2` decimal(19,6) DEFAULT NULL,
  `SpecPrice` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfIPI` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfPIS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `CSTfCOFINS` varchar(2) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `ExLineNo` varchar(10) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL,
  `isSrvCall` char(1) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb3;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `temp_ITM1`
--

DROP TABLE IF EXISTS `temp_ITM1`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `temp_ITM1` (
  `ItemCode` varchar(20) DEFAULT NULL,
  `PriceList` int DEFAULT NULL,
  `Price` decimal(6,0) DEFAULT NULL,
  `Currency` varchar(3) DEFAULT NULL,
  `Ovrwritten` char(1) DEFAULT NULL,
  `Factor` decimal(6,0) DEFAULT NULL,
  `LogInstance` int DEFAULT NULL,
  `ObjType` int DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Table structure for table `temp_OITM`
--

DROP TABLE IF EXISTS `temp_OITM`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `temp_OITM` (
  `ItemCode` varchar(20) DEFAULT NULL,
  `Valid` char(1) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping events for database 'ultimau5_atilive'
--

--
-- Dumping routines for database 'ultimau5_atilive'
--
/*!50003 DROP PROCEDURE IF EXISTS `GetAllItemsLastPurchase` */;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetAllItemsLastPurchase`()
BEGIN
    SELECT 
		T0.DocNum AS LastDocNum,
        T0.Comments,
        T1.ItemCode,
        T1.Dscription AS ItemDescription,
        T0.CardCode, T2.CardName, T2.Address,
        (T1.Price * 1.12) AS LastPrice,
        T0.DocCur AS Currency,
        T0.DocDate AS LastPurchaseDate
        
        
    FROM POR1 T1
    INNER JOIN OPOR T0 ON T1.DocEntry = T0.DocEntry
    INNER JOIN OCRD T2 ON  T2.CardCode = T0.CardCode
    GROUP BY T0.DocNum, T0.Comments
    ORDER BY T1.ItemCode ASC, T1.DocDate Desc;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
/*!50003 DROP PROCEDURE IF EXISTS `GetCompletedToolsOrder` */;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetCompletedToolsOrder`()
BEGIN
    SELECT 
        o.SRID,
        o.contractID,
        o.custmrName AS CustomerName,
        o.addrName AS SiteAddress,
        o.technician AS LeadTech,
        o.subject AS Subject,
        o.StartDate AS StartDate,
        o.StartTime AS StartTime,
        o.EndDate AS EndDate,
        o.EndTime AS EndTime,
        o.status AS StatusCode,
        o.callType AS ServiceType,
        o.equipType AS EquipmentType
    FROM `OSCL` o
    -- Explicitly qualify table alias and wrap string literal if applicable
    WHERE (o.`status` = 1 OR o.`status` = '1')  
      
      -- Fully qualify the subquery correlation line
      AND EXISTS (
          SELECT 1 
          FROM `OSCL_TOOL` ot 
          WHERE ot.`SRID` = o.`SRID` 
            AND ot.`STATUS` = 'ASSIGNED'
      )
          
    ORDER BY o.createDate DESC, o.createTime DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
/*!50003 DROP PROCEDURE IF EXISTS `GetContactInfo` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetContactInfo`(
    -- Changed COLLATE to utf8mb3_general_ci to match OCRD table default
    IN pCardCode VARCHAR(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci
)
BEGIN
    SELECT 
        OCRD.CardCode, 
        OCRD.CardName, 
        OCRD.CardType, 
        OCRD.Address, 
        OCRD.CntctPrsn,
        OCPR.Tel1,
                OCPR.Tel2,
        OCPR.E_MailL,
        OCPR.CntctCode, 
        OCPR.Name AS ContactName, 
        OCRD.LicTradNum, 
        OCRD.ListNum, 
        OCRD.Currency, 
        OCRD.GroupNum, 
        OCTG.PymntGroup, 
        OCRD.Discount, 
        OCRD.SlpCode, 
        OSLP.SlpName, 
        OCRD.Balance, 
        OCRD.ECVatGroup, 
        OVTG.Code AS VatCode, 
        OVTG.Name AS VatName, 
        OVTG.Rate AS VatRate, 
        OVTG.Account AS VatAccount, 
        OCRD.wtCode AS WTCode, 
        OWHT.WTName, 
        OWHT.Rate AS WTRate, 
        OWHT.Account AS WTAccount 
    FROM OCRD 
    -- Forced collation on joins to prevent "Illegal Mix" during the lookup phase
    LEFT JOIN OCPR ON OCRD.CardCode = OCPR.CardCode COLLATE utf8mb3_general_ci
        AND OCRD.CntctPrsn = OCPR.Name COLLATE utf8mb3_general_ci
    LEFT JOIN OCTG ON OCRD.GroupNum = OCTG.GroupNum 
    LEFT JOIN OVTG ON OCRD.ECVatGroup = OVTG.Code 
    LEFT JOIN OSLP ON OCRD.SlpCode = OSLP.SlpCode 
    LEFT JOIN OWHT ON OCRD.wtCode = OWHT.wtCode 
    -- Simplest comparison: Both are now general_ci
    WHERE OCRD.CardCode = pCardCode;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetCustomerSalesOrdersByItem` */;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetCustomerSalesOrdersByItem`(
    IN p_CardCode VARCHAR(50)
)
BEGIN
    SELECT 
        t0.DocEntry, 
        t0.DocNum, 
        t0.CntctCode,
        t1.ItemCode,
        t1.Dscription AS ItemDescription,
        t1.Quantity,
        t1.Price,
        t1.LineTotal
    FROM ORDR t0
    INNER JOIN RDR1 t1 ON t0.DocEntry = t1.DocEntry
    WHERE t0.CardCode = p_CardCode 
      AND t1.ItemCode = 'SUBSERV000123'
      AND t0.DocStatus <> '1'
    ORDER BY t0.DocEntry DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
/*!50003 DROP PROCEDURE IF EXISTS `GetCustomerSalesOrdersBySubserv124` */;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetCustomerSalesOrdersBySubserv124`(
    IN p_CardCode VARCHAR(50)
)
BEGIN
    SELECT 
        t0.DocEntry, 
        t0.DocNum, 
        t0.CntctCode,
        t1.ItemCode,
        t1.Dscription AS ItemDescription,
        t1.Quantity,
        t1.Price,
        t1.LineTotal
    FROM ORDR t0
    INNER JOIN RDR1 t1 ON t0.DocEntry = t1.DocEntry
    WHERE t0.CardCode = p_CardCode 
      AND t1.ItemCode = 'SUBSERV000124'
      AND t0.DocStatus <> '1'
    ORDER BY t0.DocEntry DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
/*!50003 DROP PROCEDURE IF EXISTS `GetDeliveriesBySpec` */;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetDeliveriesBySpec`(
    IN pDateFrom DATE,
    IN pItemGroupCode INT,
    IN pSpecKeyword VARCHAR(100),
    IN pMode VARCHAR(10)
)
BEGIN
    DECLARE vSearchSpec VARCHAR(150);
    SET vSearchSpec = CONCAT('%', pSpecKeyword, '%');

    IF LOWER(pMode) = 'summary' THEN
        -- Summary Mode: Aggregated by ItemCode
        SELECT 
            t2.ItemCode,
            t3.ItemName,
            COUNT(*) AS total_deliveries,
            SUM(t2.Quantity) AS total_quantity
        FROM ODLN t1
        INNER JOIN DLN1 t2 ON t2.DocEntry = t1.DocEntry
        INNER JOIN OITM t3 ON t2.ItemCode = t3.ItemCode
        INNER JOIN OCRD t4 ON t4.CardCode = t1.CardCode
        WHERE 
            t1.DocDate >= pDateFrom
            AND t3.ItmsGrpCod = pItemGroupCode
            AND (pSpecKeyword = '' OR t3.Spec LIKE vSearchSpec)
        GROUP BY 
            t2.ItemCode, t3.ItemName
        ORDER BY 
            total_quantity DESC;

    ELSE
        -- Details Mode: Show every delivery line
        SELECT 
            t1.DocNum, 
            t1.DocDate, 
            t1.CardCode, 
            t4.CardName, 
            t2.ItemCode, 
            t2.Dscription, 
            t3.ItemName, 
            t2.Quantity, 
            t3.ItmsGrpCod, 
            t3.Spec
        FROM ODLN t1
        INNER JOIN DLN1 t2 ON t2.DocEntry = t1.DocEntry
        INNER JOIN OITM t3 ON t2.ItemCode = t3.ItemCode
        INNER JOIN OCRD t4 ON t4.CardCode = t1.CardCode
        WHERE 
            t1.DocDate >= pDateFrom
            AND t3.ItmsGrpCod = pItemGroupCode
            AND (pSpecKeyword = '' OR t3.Spec LIKE vSearchSpec)
        ORDER BY 
            t1.DocDate ASC;
    END IF;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
/*!50003 DROP PROCEDURE IF EXISTS `GetEquipmentByCardCode` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetEquipmentByCardCode`(
    IN p_CardCode VARCHAR(15)
)
BEGIN
    SELECT 
        e.insID,
        e.itemCode,
        e.itemName,
        e.manufSN AS Manufacturer_Serial,
        e.machine AS MRI_Machine,
        e.internalSN AS Internal_Serial,
        e.warranty AS Warranty_Type,
        e.wrrntyStrt AS Warranty_Start,
        e.wrrntyEnd AS Warranty_End,
        e.contract AS Contract,
        c.StartDate,
        c.EndDate,
        c.DocNum,
        e.instLction AS Installation_Location
        
    FROM OINS e
    INNER JOIN OCTR c ON c.ContractID = e.contract
    
    WHERE `customer` = p_CardCode AND `contract` = 1
    
    ORDER BY itemName ASC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetEquipmentByCardCode2` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetEquipmentByCardCode2`(
    IN p_CardCode VARCHAR(15)
)
BEGIN
    SELECT 
        e.insID,
        e.itemCode,
        e.itemName,
        e.manufSN AS Manufacturer_Serial,
        e.machine AS MRI_Machine,
        e.internalSN AS Internal_Serial,
        e.warranty AS Warranty_Type,
        e.wrrntyStrt AS Warranty_Start,
        e.wrrntyEnd AS Warranty_End,
        e.contract AS Contract,
        c.StartDate,
        c.EndDate,
        c.DocNum,
        e.instLction AS Installation_Location,
        
        -- Latest Status: Select the status from the subquery directly
        COALESCE(oed.Status, oiu.Status) AS Current_Status,
        CASE 
            WHEN oed.Status IS NOT NULL THEN 'Outdoor'
            WHEN oiu.Status IS NOT NULL THEN 'Indoor'
            ELSE ' '
        END AS Status_Source

    FROM OINS e
    INNER JOIN OCTR c ON c.ContractID = e.contract
    
    -- Join for Outdoor Units (using subquery to get only the LATEST row)
    LEFT JOIN (
        SELECT OutSerial, Status 
        FROM OSCL_EquipmentDetails 
        ORDER BY SRID DESC
        LIMIT 1 -- Note: In a real environment, you might need a correlated subquery 
                -- or a partition if you have multiple serials.
    ) oed ON e.manufSN = oed.OutSerial
    
    -- Join for Indoor Units
    LEFT JOIN (
        SELECT IndoorSerial, Status 
        FROM OSCL_IndoorUnits 
        ORDER BY IndoorUnitID DESC
        LIMIT 1
    ) oiu ON e.internalSN = oiu.IndoorSerial
    
    WHERE e.customer = p_CardCode 
      AND e.contract = 1
    ORDER BY e.itemName ASC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetEquipmentByCardCode3` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetEquipmentByCardCode3`(
    IN p_CardCode VARCHAR(15)
)
BEGIN
    SELECT 
        e.insID,
        e.itemCode,
        e.itemName,
        e.manufSN AS Manufacturer_Serial,
        e.machine AS MRI_Machine,
        e.internalSN AS Internal_Serial,
        e.warranty AS Warranty_Type,
        e.wrrntyStrt AS Warranty_Start,
        e.wrrntyEnd AS Warranty_End,
        e.contract AS Contract,
        c.StartDate,
        c.EndDate,
        c.DocNum,
        e.instLction AS Installation_Location,
        
        -- Raw image name/path from OINS
        e.img,
        
      
        
        -- Defaults Current_Status to 1 if both derived statuses are NULL
        COALESCE(oed.Status, oiu.Status, 1) AS Current_Status,

        -- Returns 'Default' when defaulting to 1
        CASE 
            WHEN oed.Status IS NOT NULL THEN 'Outdoor'
            WHEN oiu.Status IS NOT NULL THEN 'Indoor'
            ELSE 'Default'
        END AS Status_Source

    FROM OINS e
    INNER JOIN OCTR c ON c.ContractID = e.contract
    
    -- Join for Outdoor Units (Get max SRID per OutSerial)
    LEFT JOIN (
        SELECT ed1.OutSerial, ed1.Status
        FROM OSCL_EquipmentDetails ed1
        INNER JOIN (
            SELECT OutSerial, MAX(SRID) AS MaxSRID
            FROM OSCL_EquipmentDetails
            WHERE OutSerial IS NOT NULL AND OutSerial != ''
            GROUP BY OutSerial
        ) ed2 ON ed1.OutSerial = ed2.OutSerial AND ed1.SRID = ed2.MaxSRID
    ) oed ON e.manufSN = oed.OutSerial
    
    -- Join for Indoor Units (Get max IndoorUnitID per IndoorSerial)
    LEFT JOIN (
        SELECT iu1.IndoorSerial, iu1.Status
        FROM OSCL_IndoorUnits iu1
        INNER JOIN (
            SELECT IndoorSerial, MAX(IndoorUnitID) AS MaxID
            FROM OSCL_IndoorUnits
            WHERE IndoorSerial IS NOT NULL AND IndoorSerial != ''
            GROUP BY IndoorSerial
        ) iu2 ON iu1.IndoorSerial = iu2.IndoorSerial AND iu1.IndoorUnitID = iu2.MaxID
    ) oiu ON e.internalSN = oiu.IndoorSerial
    
    WHERE e.customer = p_CardCode 
      AND e.contract = 1
    ORDER BY e.itemName ASC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetImagesBySRID` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetImagesBySRID`(
    IN p_srid INT
)
BEGIN
    SELECT SRID, name,  path  FROM `ultimau5_atilive`.`IMGESR`
WHERE imageID IN (
    SELECT MAX(imageID) 
    FROM `ultimau5_atilive`.`IMGESR` 
    WHERE `SRID` = p_srid
    GROUP BY `SRID`, `name`, `path`
);
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetInProgressToolsOrder` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetInProgressToolsOrder`()
BEGIN
    SELECT 
        o.SRID,
        o.contractID,
        o.custmrName AS CustomerName,
        o.addrName AS SiteAddress,
        o.technician AS LeadTech,
        o.subject AS Subject,
        o.StartDate AS StartDate,
        o.StartTime AS StartTime,
        o.EndDate AS EndDate,
        o.EndTime AS EndTime,
        o.status AS StatusCode,
        o.callType AS ServiceType,
        o.equipType AS EquipmentType
    FROM `OSCL` o
    -- 1. Job is STILL active/open (not yet closed or completed)
    WHERE (o.`status` <> 1 OR o.`status` <> '1' OR o.`status` is null)  
      
      -- 2. Tool Check: Tools have already been assigned and are currently out in the field
      AND EXISTS (
          SELECT 1 
          FROM `OSCL_TOOL` ot 
          WHERE ot.`SRID` = o.`SRID` 
            AND ot.`STATUS` = 'ASSIGNED'
      )
          
    ORDER BY o.createDate DESC, o.createTime DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetItemBalancesWithVatPrice2` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetItemBalancesWithVatPrice2`(IN groupID INT)
BEGIN
    SELECT 
        I.ItemCode, 
        I.ItemName, 
        I.BuyUnitMsr, I.ItmsGrpCod,
        COALESCE(LH.PriceAfVAT, 0) as LastVatPrice,
        COALESCE(LH.DocCur, 'PHP') as Currency,
        COALESCE(LH.MasterVendorName, LH.HeaderCardName) as LastVendor, 
        LH.DocDate as LastPurDate,
        COALESCE(P.onPO, 0) as onPO,
        COALESCE(S.OnSO, 0) as OnSO,
        COALESCE(STK.InStock, 0) as InStock
    FROM OITM I
    -- Keep this INNER JOIN because every item MUST have a group
    INNER JOIN OITB B ON I.ItmsGrpCod = B.ItmsGrpCod
    
    -- CHANGE TO LEFT JOIN: Last Price History
    LEFT JOIN (
        SELECT r1.ItemCode, r1.PriceAfVAT, r0.DocCur, r0.DocDate,
               r0.CardName as HeaderCardName, oc.CardName as MasterVendorName
        FROM POR1 r1
        INNER JOIN OPOR r0 ON r1.DocEntry = r0.DocEntry
        LEFT JOIN OCRD oc ON r0.CardCode = oc.CardCode
        WHERE r1.DocID IN (SELECT MAX(DocID) FROM POR1 GROUP BY ItemCode)
    ) LH ON I.ItemCode = LH.ItemCode

    -- CHANGE TO LEFT JOIN: Open PO Quantities
    LEFT JOIN (
        SELECT p1.ItemCode, SUM(p1.OpenQty) as onPO
        FROM POR1 p1
        INNER JOIN OPOR p0 ON p0.DocEntry = p1.DocEntry
        WHERE p0.CANCELED = 'N' AND p1.LineStatus = 0
        GROUP BY p1.ItemCode
    ) P ON I.ItemCode = P.ItemCode

    -- CHANGE TO LEFT JOIN: Open Sales Orders
    LEFT JOIN (
        SELECT ItemCode, SUM(OpenQty) as OnSO 
        FROM RDR1 
        WHERE LineStatus = 0 
        GROUP BY ItemCode
    ) S ON I.ItemCode = S.ItemCode

    -- CHANGE TO LEFT JOIN: Stock Calculation
    LEFT JOIN (
        SELECT ItemCode, SUM(Qty) as InStock
        FROM (
            SELECT ItemCode, Quantity as Qty FROM PDN1 WHERE LineStatus = 0
            UNION ALL SELECT ItemCode, -Quantity FROM RPD1 WHERE LineStatus = 0
            UNION ALL SELECT ItemCode, -Quantity FROM DLN1 WHERE LineStatus = 0
            UNION ALL SELECT ItemCode, Quantity FROM RDN1 WHERE LineStatus = 0
        ) AS Movements GROUP BY ItemCode
    ) STK ON I.ItemCode = STK.ItemCode

    -- Apply the exact filters you used in your successful SELECT query
    WHERE I.itmsGrpCod = groupID 
      AND I.PrchseItem = 'Y' 
      AND I.Valid = 'Y'
    ORDER BY I.ItemCode;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetItemBalancesWithVatPrice3` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetItemBalancesWithVatPrice3`(IN groupID INT)
BEGIN
    SELECT 
        I.ItemCode, 
        I.ItemName, 
        I.BuyUnitMsr, 
        I.ItmsGrpCod,
        COALESCE(LH.PriceAfVAT, 0) AS LastVatPrice,
        COALESCE(LH.DocCur, 'PHP') AS Currency,
        COALESCE(LH.MasterVendorName, LH.HeaderCardName) AS LastVendor, 
        LH.DocDate AS LastPurDate,
        COALESCE(P.onPO, 0) AS onPO,
        COALESCE(S.OnSO, 0) AS OnSO,

        -- InStock Formula: GRPO - GR - DR + SR
        (
            COALESCE(grpo.OnGRPO, 0)
            - COALESCE(gr.OnGR, 0)
            - COALESCE(dr.OnDR, 0)
            + COALESCE(sr.OnSR, 0)
        ) AS InStock,

        -- Available Formula: InStock + OnPO - OnSO
        (
            (
                COALESCE(grpo.OnGRPO, 0)
                - COALESCE(gr.OnGR, 0)
                - COALESCE(dr.OnDR, 0)
                + COALESCE(sr.OnSR, 0)
                + COALESCE(P.onPO, 0)
            ) 
            - COALESCE(S.OnSO, 0)
        ) AS Available

    FROM OITM I
    INNER JOIN OITB B ON I.ItmsGrpCod = B.ItmsGrpCod
    
    -- Last Purchase Price & Vendor History
    LEFT JOIN (
        SELECT r1.ItemCode, r1.PriceAfVAT, r0.DocCur, r0.DocDate,
               r0.CardName AS HeaderCardName, oc.CardName AS MasterVendorName
        FROM POR1 r1
        INNER JOIN OPOR r0 ON r1.DocEntry = r0.DocEntry
        LEFT JOIN OCRD oc ON r0.CardCode = oc.CardCode
        WHERE r1.DocID IN (SELECT MAX(DocID) FROM POR1 GROUP BY ItemCode)
    ) LH ON I.ItemCode = LH.ItemCode

    -- Open PO Quantities
    LEFT JOIN (
        SELECT p1.ItemCode, SUM(p1.OpenQty) AS onPO
        FROM POR1 p1
        INNER JOIN OPOR p0 ON p0.DocEntry = p1.DocEntry
        WHERE p0.CANCELED = 'N' AND p1.LineStatus = 0
        GROUP BY p1.ItemCode
    ) P ON I.ItemCode = P.ItemCode

    -- Open Sales Orders
    LEFT JOIN (
        SELECT ItemCode, SUM(OpenQty) AS OnSO 
        FROM RDR1 
        WHERE LineStatus = 0 
        GROUP BY ItemCode
    ) S ON I.ItemCode = S.ItemCode

    -- Goods Receipt POs (OnGRPO)
    LEFT JOIN (
        SELECT ItemCode, SUM(Quantity) AS OnGRPO
        FROM PDN1
        WHERE LineStatus = 0
        GROUP BY ItemCode
    ) grpo ON grpo.ItemCode = I.ItemCode

    -- Goods Returns (OnGR)
    LEFT JOIN (
        SELECT ItemCode, SUM(Quantity) AS OnGR
        FROM RPD1
        WHERE LineStatus = 0
        GROUP BY ItemCode
    ) gr ON gr.ItemCode = I.ItemCode

    -- Deliveries (OnDR)
    LEFT JOIN (
        SELECT ItemCode, SUM(Quantity) AS OnDR
        FROM DLN1
        WHERE LineStatus = 0
        GROUP BY ItemCode
    ) dr ON dr.ItemCode = I.ItemCode

    -- Sales Returns (OnSR)
    LEFT JOIN (
        SELECT ItemCode, SUM(Quantity) AS OnSR
        FROM RDN1
        WHERE LineStatus = 0
        GROUP BY ItemCode
    ) sr ON sr.ItemCode = I.ItemCode

    WHERE I.ItmsGrpCod = groupID 
      AND I.PrchseItem = 'Y' 
      AND I.Valid = 'Y'
    ORDER BY I.ItemCode;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetItemBalancesWithVatPrice5` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetItemBalancesWithVatPrice5`(IN groupID INT)
BEGIN
    SELECT 
        I.ItemCode, 
        I.ItemName, 
        I.BuyUnitMsr, 
        COALESCE(LH.PriceAfVAT, 0) as LastVatPrice,
        LH.DocCur as Currency,
        -- Pulling official CardName from OCRD master table
        COALESCE(LH.MasterVendorName, LH.HeaderCardName) as LastVendor, 
        LH.DocDate as LastPurDate,
        COALESCE(P.onPO, 0) as onPO,
        COALESCE(S.OnSO, 0) as OnSO,
        COALESCE(STK.InStock, 0) as InStock
    FROM OITM I
    INNER JOIN OITB B ON I.ItmsGrpCod = B.ItmsGrpCod
    
    -- SUBQUERY: Pulls history and joins OCRD for the Vendor Name
    LEFT JOIN (
        SELECT 
            r1.ItemCode, 
            r1.PriceAfVAT, 
            r0.DocCur, 
            r0.DocDate,
            r0.CardName as HeaderCardName,
            oc.CardName as MasterVendorName
        FROM POR1 r1
        INNER JOIN OPOR r0 ON r1.DocEntry = r0.DocEntry
        -- Joining to Vendor Master Data
        LEFT JOIN OCRD oc ON r0.CardCode = oc.CardCode
        WHERE r1.DocID IN (
            SELECT MAX(DocID) 
            FROM POR1 
            GROUP BY ItemCode
        )
    ) LH ON I.ItemCode = LH.ItemCode

    -- Keep existing quantity logic
    LEFT JOIN (
        SELECT p1.ItemCode, SUM(p1.OpenQty) as onPO
        FROM POR1 p1
        INNER JOIN OPOR p0 ON p0.DocEntry = p1.DocEntry
        WHERE p0.wddStatus = 'Y' AND p1.LineStatus = 0
        GROUP BY p1.ItemCode
    ) P ON I.ItemCode = P.ItemCode

    LEFT JOIN (
        SELECT ItemCode, SUM(OpenQty) as OnSO FROM RDR1 WHERE LineStatus = 0 GROUP BY ItemCode
    ) S ON I.ItemCode = S.ItemCode

    LEFT JOIN (
        SELECT ItemCode, SUM(Qty) as InStock
        FROM (
            SELECT ItemCode, Quantity as Qty FROM PDN1 WHERE LineStatus = 0
            UNION ALL SELECT ItemCode, -Quantity FROM RPD1 WHERE LineStatus = 0
            UNION ALL SELECT ItemCode, -Quantity FROM DLN1 WHERE LineStatus = 0
            UNION ALL SELECT ItemCode, Quantity FROM RDN1 WHERE LineStatus = 0
        ) AS Movements GROUP BY ItemCode
    ) STK ON I.ItemCode = STK.ItemCode

    WHERE I.PrchseItem = 'Y' AND I.Valid = 'Y' AND I.itmsGrpCod = groupID
    ORDER BY I.ItemCode;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetL300LastPurchaseSummary` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetL300LastPurchaseSummary`()
BEGIN
    WITH RankedPurchases AS (
        SELECT 
            T0.DocNum AS LastDocNum,
            T0.Comments,
            T1.ItemCode,
            T1.Dscription AS ItemDescription,
            T0.CardCode, 
            T2.CardName, 
            T2.Address,
            (T1.Price * 1.12) AS LastPrice,
            T0.DocCur AS Currency,
            T0.DocDate AS LastPurchaseDate,
            /* This assigns '1' to the most recent purchase per ItemCode */
            ROW_NUMBER() OVER (PARTITION BY T1.ItemCode ORDER BY T0.DocDate DESC, T0.DocNum DESC) as RowNum
        FROM POR1 T1
        INNER JOIN OPOR T0 ON T1.DocEntry = T0.DocEntry
        INNER JOIN OCRD T2 ON T2.CardCode = T0.CardCode
        WHERE T1.Dscription LIKE '%L300%' OR T1.ItemCode LIKE '%L300%'
    )
    SELECT 
        LastDocNum,
        Comments,
        ItemCode,
        ItemDescription,
        CardCode,
        CardName,
        Address,
        LastPrice,
        Currency,
        LastPurchaseDate
    FROM RankedPurchases
    WHERE RowNum = 1
    ORDER BY ItemCode ASC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetL300LastPurchaseSummary2` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetL300LastPurchaseSummary2`()
BEGIN
    WITH RankedPurchases AS (
        SELECT 
            T0.DocNum AS LastDocNum,
            T0.Comments,
            T1.ItemCode,
            T1.Dscription AS ItemDescription,
            T0.CardCode, 
            T2.CardName, 
            T2.Address,
            (T1.Price * 1.12) AS LastPrice,
            T0.DocCur AS Currency,
            T0.DocDate AS LastPurchaseDate,
            /* This ranks items: 1 is the most recent purchase */
            ROW_NUMBER() OVER (
                PARTITION BY T1.ItemCode 
                ORDER BY T0.DocDate DESC, T0.DocNum DESC
            ) AS ItemRank
        FROM POR1 T1
        INNER JOIN OPOR T0 ON T1.DocEntry = T0.DocEntry
        INNER JOIN OCRD T2 ON T2.CardCode = T0.CardCode
        /* Filters specifically for L300 related descriptions or codes */
        WHERE T1.Dscription LIKE '%L300%' OR T1.ItemCode LIKE '%L300%'
    )
    SELECT 
        LastDocNum,
        Comments,
        ItemCode,
        ItemDescription,
        CardCode,
        CardName,
        Address,
        LastPrice,
        Currency,
        LastPurchaseDate
    FROM RankedPurchases
    WHERE ItemRank = 1
    ORDER BY ItemCode ASC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetLastPurchaseDetails` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetLastPurchaseDetails`(IN targetItemCode VARCHAR(20))
BEGIN
    SELECT 
        T1.ItemCode,
        T1.Dscription AS ItemName,
        T0.CardCode AS VendorCode,
        T0.CardName AS VendorName,
        T1.Price AS LastPurchasePrice,
        T0.DocCur AS Currency,
        T0.DocDate AS LastPurchaseDate,
        T0.DocNum AS PurchaseOrderNumber
    FROM OPOR T0
    INNER JOIN POR1 T1 ON T0.DocEntry = T1.DocEntry
    WHERE  T0.CANCELED = 'N'  -- Exclude canceled documents
    ORDER BY T0.DocDate DESC, T0.DocEntry DESC
    LIMIT 1;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetPendingLogisticsOrders` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetPendingLogisticsOrders`( 
)
BEGIN
    SELECT 
        o.SRID,
        o.DocNum,
        o.custmrName AS CustomerName,
        o.subject AS Subject,
        o.createDate AS CreateDate,
        o.status AS StatusCode
    FROM `OSCL` o
    WHERE o.status <> 1  -- Exclude closed tickets
    
      -- Tool Keeper check
      AND o.SRID NOT IN (
          SELECT DISTINCT ot.SRID 
          FROM `OSCL_TOOL` ot 
          WHERE ot.STATUS = 'ASSIGNED'
      )
      
      -- Logistics Manager check
      AND o.SRID NOT IN (
          SELECT DISTINCT ova.SRID 
          FROM `OSCL_VEHICLE` ova 
          WHERE ova.STATUS = 'DISPATCHED'
      )
      
      
      
    ORDER BY o.createDate DESC, o.createTime DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetPendingToolOrders` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetPendingToolOrders`()
BEGIN
    SELECT 
        o.SRID,
        o.contractID,
        o.custmrName AS CustomerName,
        o.addrName AS SiteAddress,
        o.technician AS LeadTech,
        o.subject AS Subject,
        o.createDate AS CreateDate,
        o.createTime as CreateTime,
        o.status AS StatusCode,
        o.callType AS ServiceType,
        o.equipType AS EquipmentType
    FROM `OSCL` o
    WHERE (o.status <> 1 OR o.status IS NULL)  -- Handles active status codes and unassigned NULLs
    
      -- Tool Check: Ticket does not exist in your active assignments bridge table
      AND o.SRID NOT IN (
          SELECT DISTINCT ot.SRID 
          FROM `OSCL_TOOL` ot 
          WHERE ot.STATUS = 'ASSIGNED'
      )
          
    ORDER BY o.createDate DESC, o.createTime DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetPOApprovals2` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetPOApprovals2`(IN p_FilterStatus VARCHAR(20))
BEGIN
    SELECT 
        a.WddCode AS 'ApprovalID',
        CASE 
            WHEN a.ObjType = '2' THEN 'Purchase Order'
            ELSE 'Other'
        END AS 'DocumentType', a.DocEntry,
        COALESCE(po.DocNum, CAST(a.DocEntry AS CHAR)) AS 'DocNumber',
        COALESCE(bp.CardName, po.CardName) AS 'VendorName', --  Updated to grab master CardName from OCRD
        po.DocTotal AS 'TotalAmount',
        po.DocCur AS 'Currency',
        CONCAT(u.FNAME, ' ', u.LNAME) AS 'Originator',
        
        (SELECT GROUP_CONCAT(CONCAT(u2.FNAME, ' ', u2.LNAME) SEPARATOR ', ')
         FROM WDD1 w1
         INNER JOIN USER u2 ON w1.UserID = u2.USER_ID
         WHERE w1.WddCode = a.WddCode AND w1.Status = 'Y') AS 'ApprovedByNames',

        (SELECT GROUP_CONCAT(CONCAT(u3.FNAME, ' ', u3.LNAME) SEPARATOR ', ')
         FROM WDD1 w2
         INNER JOIN USER u3 ON w2.UserID = u3.USER_ID
         WHERE w2.WddCode = a.WddCode AND w2.Status != 'Y') AS 'PendingApproverNames',

        (SELECT COUNT(*) FROM WDD1 WHERE WddCode = a.WddCode) AS 'TotalNeeded',
        (SELECT COUNT(*) FROM WDD1 WHERE WddCode = a.WddCode AND Status != 'Y') AS 'PendingCount',

        a.Remarks AS 'DraftRemarks',
        CASE 
            WHEN a.Status = 'W' THEN 'Pending'
            WHEN a.Status = 'Y' THEN 'Approved'
            WHEN a.Status = 'N' THEN 'Rejected'
            WHEN a.Status = 'R' THEN 'Request'
            ELSE 'Unknown'
        END AS 'DecisionStatus',
        a.CreateDate AS 'RequestDate'
    FROM 
        OWDD a
    LEFT JOIN 
        OPOR po ON a.DocEntry = po.DocEntry AND a.ObjType = '2'
    LEFT JOIN 
        OCRD bp ON po.CardCode = bp.CardCode --  Added JOIN to Business Partner Master Data Table
    LEFT JOIN 
        USER u ON po.UserSign = u.USER_ID
    WHERE 
        -- Parentheses here are CRITICAL to stop 'Others' from appearing
        (
            (p_FilterStatus = 'Pending' AND a.Status = 'W') OR
            (p_FilterStatus = 'Approved' AND a.Status = 'Y') OR
            (p_FilterStatus = 'Rejected' AND a.Status = 'N') OR
            (p_FilterStatus = 'Request' AND a.Status = 'R') OR
            (p_FilterStatus = 'All' OR p_FilterStatus IS NULL OR p_FilterStatus = '')
        )
        -- This AND now applies to EVERY condition inside the parentheses above
        AND a.ObjType = '2'
        
    ORDER BY 
        a.CreateDate DESC, a.CreateTime DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetPOWithPendingApprovalStatus` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetPOWithPendingApprovalStatus`(
    IN p_WddStatus VARCHAR(3),
    IN p_UserID INT
)
BEGIN
    SELECT 
        OPOR.DocEntry,
        OPOR.DocNum,
        OPOR.DocDate,
        OPOR.CardCode,
        OCRD.CardName,
        OPOR.DocTotal,
        CONCAT(creator.FNAME, ' ', creator.LNAME) AS 'CreatedBy',
        ow.WddCode AS 'ApprovalID',
        
        -- Overall Document Status
        CASE 
            WHEN ow.Status = 'W' THEN 'Pending'
            WHEN ow.Status = 'Y' THEN 'Approved'
            WHEN ow.Status = 'N' THEN 'Rejected'
            WHEN ow.Status = 'R' THEN 'Request'
            ELSE 'Not Required'
        END AS 'ApprovalStatusLabel',
        
        -- Current Logged-in User's Line Decision
        user_wdd.Status AS 'MyDecisionStatus',

        (SELECT COUNT(*) FROM WDD1 WHERE WddCode = ow.WddCode) AS 'RequiredApprovers',
        (SELECT COUNT(*) FROM WDD1 WHERE WddCode = ow.WddCode AND Status = 'Y') AS 'ApprovalsReceived',
        
        (SELECT GROUP_CONCAT(CONCAT(u.FNAME, ' ', u.LNAME) SEPARATOR ', ')
         FROM WDD1 w1
         INNER JOIN USER u ON w1.UserID = u.USER_ID
         WHERE w1.WddCode = ow.WddCode 
           AND w1.Status != 'Y') AS 'PendingApprovers',

        ow.Remarks AS 'ApprovalRemarks',
        OPOR.DocStatus
    FROM OPOR 
    INNER JOIN OCRD ON OCRD.CardCode = OPOR.CardCode
    LEFT JOIN USER creator ON OPOR.UserSign = creator.USER_ID
    LEFT JOIN OWDD ow ON OPOR.DocEntry = ow.DocEntry AND ow.ObjType = '2'
    -- Join ONLY the current user's line to determine their view
    INNER JOIN WDD1 user_wdd ON ow.WddCode = user_wdd.WddCode AND user_wdd.UserID = p_UserID
    WHERE 
        -- 1. All records for this approver
        (p_WddStatus IS NULL OR p_WddStatus = '' OR p_WddStatus = 'All')

        -- 2. Pending Filter: PO is only "Pending" for this user IF their own status is still 'W'
        OR (
            (p_WddStatus = 'W' OR p_WddStatus = 'Pending') 
            AND user_wdd.Status = 'W'
        )

        -- 3. Approved Filter: PO is "Approved" for this user if their own status is 'Y'
        OR (
            (p_WddStatus = 'Y' OR p_WddStatus = 'Approved') 
            AND user_wdd.Status = 'Y'
        )

        -- 4. Request Filter: PO is in "Request" for this user ONLY IF their own status is 'R'
        OR (
            (p_WddStatus = 'R' OR p_WddStatus = 'Request') 
            AND user_wdd.Status = 'R'
        )

        -- 5. Rejected Filter: PO is "Rejected" if user rejected it or header was killed
        OR (
            (p_WddStatus = 'N' OR p_WddStatus = 'Rejected') 
            AND (user_wdd.Status = 'N' OR ow.Status = 'N')
        )
    ORDER BY OPOR.DocEntry DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetPurchaseOrdersByStatus` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_unicode_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'IGNORE_SPACE,ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetPurchaseOrdersByStatus`(IN p_WddStatus VARCHAR(1))
BEGIN
    SELECT 
        OPOR.DocEntry,
        OPOR.DocNum, 
        OPOR.DocDate, 
        OPOR.CardCode, 
        OCRD.CardName,  
        OPOR.DocTotal, 
        OPOR.DocTotalFC, 
        OPOR.Comments, 
        OPOR.NumAtCard,
        OPOR.Ref1,
        OPOR.Ref2, 
        OPOR.Project,
        OPOR.WddStatus AS Approved,  
        OPOR.DocStatus 
    FROM OPOR 
    INNER JOIN OCRD ON OCRD.CardCode = OPOR.CardCode
    WHERE 
        
        (p_WddStatus IS NULL OR p_WddStatus = '' OR OPOR.WddStatus = p_WddStatus)
    ORDER BY OPOR.DocEntry DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetPurchaseOrdersWithApprovalStatus` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetPurchaseOrdersWithApprovalStatus`(
    IN p_WddStatus VARCHAR(20) CHARACTER SET utf8mb3 COLLATE utf8mb3_bin
)
BEGIN
    SELECT 
        OPOR.DocEntry,
        OPOR.DocNum, 
        OPOR.DocDate, 
        OPOR.CardCode, 
        OCRD.CardName,  
        OPOR.DocTotal, 
        CONCAT(creator.FNAME, ' ', creator.LNAME) AS 'CreatedBy',
        ow.WddCode AS 'ApprovalID',
        
        -- Global Document Approval Status
        CASE 
            WHEN CAST(COALESCE(ow.Status, OPOR.WddStatus) AS CHAR) = 'W' THEN 'Pending'
            WHEN CAST(COALESCE(ow.Status, OPOR.WddStatus) AS CHAR) = 'Y' THEN 'Approved'
            WHEN CAST(COALESCE(ow.Status, OPOR.WddStatus) AS CHAR) = 'N' THEN 'Rejected'
            WHEN CAST(COALESCE(ow.Status, OPOR.WddStatus) AS CHAR) = 'R' THEN 'Request'
            ELSE 'Not Required'
        END AS 'ApprovalStatusLabel',

        -- Threshold & Progress Metrics
        COALESCE(ow.MaxReqr, (SELECT COUNT(*) FROM WDD1 WHERE WddCode = ow.WddCode), 1) AS 'RequiredApprovers',
        (SELECT COUNT(*) FROM WDD1 WHERE WddCode = ow.WddCode AND CAST(Status AS CHAR) = 'Y') AS 'ApprovalsReceived',
        
        -- Pending Approvers List
        (SELECT GROUP_CONCAT(CONCAT(u.FNAME, ' ', u.LNAME) SEPARATOR ', ')
         FROM WDD1 w1
         INNER JOIN USER u ON w1.UserID = u.USER_ID
         WHERE w1.WddCode = ow.WddCode 
           AND CAST(w1.Status AS CHAR) != 'Y') AS 'PendingApprovers',

        ow.Remarks AS 'ApprovalRemarks',
        OPOR.DocStatus
    FROM OPOR 
    INNER JOIN OCRD ON OCRD.CardCode = OPOR.CardCode
    LEFT JOIN USER creator ON OPOR.UserSign = creator.USER_ID
    LEFT JOIN OWDD ow ON OPOR.DocEntry = ow.DocEntry AND ow.ObjType = '2'
    WHERE 
        -- 1. All Documents
        (p_WddStatus IS NULL OR p_WddStatus = '' OR p_WddStatus = 'All')

        -- 2. Pending (Global header is 'W')
        OR (
            (p_WddStatus = 'W' OR p_WddStatus = 'Pending') 
            AND CAST(COALESCE(ow.Status, OPOR.WddStatus) AS CHAR) = 'W'
        )

        -- 3. Approved (Global header is 'Y')
        OR (
            (p_WddStatus = 'Y' OR p_WddStatus = 'Approved') 
            AND CAST(COALESCE(ow.Status, OPOR.WddStatus) AS CHAR) = 'Y'
        )

        -- 4. Rejected (Global header is 'N')
        OR (
            (p_WddStatus = 'N' OR p_WddStatus = 'Rejected') 
            AND CAST(COALESCE(ow.Status, OPOR.WddStatus) AS CHAR) = 'N'
        )

        -- 5. Request / Clarification (Global header is 'R')
        OR (
            (p_WddStatus = 'R' OR p_WddStatus = 'Request') 
            AND CAST(COALESCE(ow.Status, OPOR.WddStatus) AS CHAR) = 'R'
        )
    ORDER BY OPOR.DocEntry DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetServiceReports` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetServiceReports`(
    IN p_StatusFilter VARCHAR(50)
)
BEGIN
    SELECT 
        o.SRID, 
        o.subject, 
        
        o.custmrName, 
        o.AddrName, 
       
        o.contractID, 
        o.callType, 
        o.equipType,
        o.createDate, 
        o.createTime, 
        COALESCE(tech_crew.LeadTechnicianName, '') AS LeadTechnicianName,
        COALESCE(tech_crew.CrewSupportNames, '') AS CrewSupportNames,
         COALESCE(tech_crew.LeadStatus, '') AS LeadJobStatus,
        o.insID, 
        o.technician, 
        o.StartDate, 
        o.StartTime, 
        o.EndDate, 
        o.EndTime, 
        o.Duration, 
        o.signature1, 
        o.signature2,
        o.signature3, 
        o.acknowledgeby, 
         o.acknowledgeby2,
          o.acknowledgeby3, 
        o.designation, 
         o.designation2, 
          o.designation3, 
        o.signedDateTime,
        o.signedDateTime2,
        o.signedDateTime3,
        o.technician2, 
        o.technician3, 
        o.technician4, 
        o.driver_name, 
        o.plate_no, 
        o.servicesRendered,
        c.Name AS ContactName, 
        c.Address AS ContactAddress,
        o.Status,
        o.Remarks,
        o.assignedby,
        o.customer, 
         o.contctCode
        
        
       
    FROM 
        `ultimau5_atilive`.`OSCL` o
    INNER JOIN 
        `ultimau5_atilive`.`OCRD` r ON r.CardCode = o.customer 
    LEFT JOIN 
        `ultimau5_atilive`.`OCPR` c ON c.CntctCode = o.contctCode AND c.CardCode = o.customer
        
    LEFT JOIN (
        SELECT 
            t.SRID,
            MAX(CASE WHEN t.IS_PRIMARY = 'Y' THEN CONCAT(tp.FIRST_NAME, ' ', tp.LAST_NAME) END) AS LeadTechnicianName,
            MAX(CASE WHEN t.IS_PRIMARY = 'Y' THEN t.STATUS END) AS LeadStatus,
            GROUP_CONCAT(
                CASE WHEN t.IS_PRIMARY = 'N' THEN CONCAT(tp.FIRST_NAME, ' ', tp.LAST_NAME) END 
                ORDER BY tp.FIRST_NAME ASC, tp.LAST_NAME ASC 
                SEPARATOR ', '
            ) AS CrewSupportNames
        FROM 
            `ultimau5_atilive`.`OSCL_TECHNICIAN` t
        INNER JOIN 
            `ultimau5_atilive`.`TECHNICIAN_PROFILE` tp ON t.TECH_ID = tp.TECH_ID
        GROUP BY 
            t.SRID
    ) tech_crew ON tech_crew.SRID = o.SRID

    WHERE 
       (
          -- Option A: Show ALL records when parameter is explicitly 'ALL'
          p_StatusFilter = 'ALL'
          
          -- Option B: Closed / Completed
          OR ( (p_StatusFilter = 'Completed' OR p_StatusFilter = 'COMPLETED') AND CAST(o.Status AS SIGNED) = 1 )
          
          -- Option C: Arrived
          OR ( p_StatusFilter = 'Arrived' AND CAST(o.Status AS SIGNED) <> 1 AND UPPER(COALESCE(tech_crew.LeadStatus, '')) = 'ARRIVED' )
          
          -- Option D: In Progress
          OR ( p_StatusFilter = 'In Progress' AND CAST(o.Status AS SIGNED) <> 1 AND UPPER(COALESCE(tech_crew.LeadStatus, '')) = 'IN_PROGRESS' )
          
          -- Option E: Unassigned / Blank (Triggers on NULL, '', 'Unassigned', or 'Unassigned (Blank)')
          OR ( (p_StatusFilter IS NULL OR p_StatusFilter = '' OR p_StatusFilter = 'Unassigned' OR p_StatusFilter = 'Unassigned (Blank)') 
               AND CAST(o.Status AS SIGNED) IS NULL
               AND COALESCE(tech_crew.LeadStatus, '') = '' )
          
          -- Option F: Assigned / Open
          OR ( (p_StatusFilter = 'Assigned' OR p_StatusFilter = 'ASSIGNED') 
               AND CAST(o.Status AS SIGNED) <> 1 
               AND COALESCE(tech_crew.LeadStatus, '') <> '' 
               AND UPPER(COALESCE(tech_crew.LeadStatus, '')) NOT IN ('ARRIVED', 'IN_PROGRESS') )
        )

    ORDER BY 
        o.SRID DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetServiceReportsByCardCode` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetServiceReportsByCardCode`(
    IN p_CardCode VARCHAR(50) -- Input parameter for the customer code
)
BEGIN
    SELECT 
        o.SRID, 
        o.subject, 
        o.customer, 
        o.custmrName, 
        o.AddrName, 
        o.contctCode, 
        o.contractID, 
        o.callType, 
        o.createDate, 
        o.createTime, 
        o.insID, 
        o.technician, 
        o.StartDate, 
        o.StartTime, 
        o.EndDate, 
        o.EndTime, 
        o.Duration, 
        o.signature1, 
        o.acknowledgeby, 
        o.designation, 
        o.signedDateTime,
        o.technician2, 
        o.technician3, 
        o.technician4, 
        o.driver_name, 
        o.plate_no, 
        o.servicesRendered,
        c.Name AS ContactName, 
        c.Address AS ContactAddress,
        o.Status,
        o.Remarks,
        o.assignedby,
        
        -- Clean string values returned to your Appsmith dashboard view
        COALESCE(tech_crew.LeadTechnicianName, '') AS LeadTechnicianName,
        COALESCE(tech_crew.CrewSupportNames, '') AS CrewSupportNames,
        COALESCE(tech_crew.LeadStatus, '') AS LeadJobStatus
    FROM 
        `ultimau5_atilive`.`OSCL` o
    INNER JOIN 
        `ultimau5_atilive`.`OCRD` r ON r.CardCode = o.customer 
    LEFT JOIN 
        `ultimau5_atilive`.`OCPR` c ON c.CntctCode = o.contctCode AND c.CardCode = o.customer
        
    -- Subquery safely aggregates using the combined names
    LEFT JOIN (
        SELECT 
            t.SRID,
            -- Evaluates and extracts the combined full name of the primary lead tech
            MAX(CASE WHEN t.IS_PRIMARY = 'Y' THEN CONCAT(tp.FIRST_NAME, ' ', tp.LAST_NAME) END) AS LeadTechnicianName,
            MAX(CASE WHEN t.IS_PRIMARY = 'Y' THEN t.STATUS END) AS LeadStatus,
            
            -- Gathers and glues supporting crew names together into a comma-separated list
            GROUP_CONCAT(
                CASE WHEN t.IS_PRIMARY = 'N' THEN CONCAT(tp.FIRST_NAME, ' ', tp.LAST_NAME) END 
                ORDER BY tp.FIRST_NAME ASC, tp.LAST_NAME ASC 
                SEPARATOR ', '
            ) AS CrewSupportNames
        FROM 
            `ultimau5_atilive`.`OSCL_TECHNICIAN` t
        INNER JOIN 
            `ultimau5_atilive`.`TECHNICIAN_PROFILE` tp ON t.TECH_ID = tp.TECH_ID
        GROUP BY 
            t.SRID
    ) tech_crew ON tech_crew.SRID = o.SRID
    
    WHERE 
        o.customer = p_CardCode -- Filters results explicitly by the provided CardCode
    
    ORDER BY 
        o.SRID DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `getSOperCardCodePM` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `getSOperCardCodePM`(
    IN p_CardCode VARCHAR(50)
)
BEGIN
    SELECT 
        t0.DocEntry, 
        t0.DocNum, 
        t0.CntctCode,
        t1.ItemCode,
        t1.Dscription AS ItemDescription,
        t1.Quantity,
        t1.Price,
        t1.LineTotal
    FROM ORDR t0
    INNER JOIN RDR1 t1 ON t0.DocEntry = t1.DocEntry
    WHERE t0.CardCode = p_CardCode 
      AND t1.ItemCode = 'SRVAIRC000018'
      AND t0.DocStatus <> '1'
    ORDER BY t0.DocEntry DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetTotalPMPerformed` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetTotalPMPerformed`(
    IN p_CardCode VARCHAR(50)
)
BEGIN
    SELECT 
        COUNT(SRID) AS TotalPMPerformed
    FROM OSCL
    WHERE callType = 'PM' 
      AND status = 1
      AND customer = p_CardCode;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetTotalRepairPerformed` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetTotalRepairPerformed`(
    IN p_CardCode VARCHAR(50)
)
BEGIN
    SELECT 
        COUNT(SRID) AS TotalRepairPerformed
    FROM OSCL
    WHERE callType = 'Repair' 
      AND status = 1
      AND customer = p_CardCode;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `GetTotalTSPerformed` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `GetTotalTSPerformed`(
    IN p_CardCode VARCHAR(50)
)
BEGIN
    SELECT 
        COUNT(SRID) AS TotalPMPerformed
    FROM OSCL
    WHERE callType = 'TS' 
      AND status = 1
      AND customer = p_CardCode;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `get_dr_with_sq_so_byItemGroup_SalesPerson` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `get_dr_with_sq_so_byItemGroup_SalesPerson`(
    IN p_ItemGroupCode INT
)
BEGIN
    SELECT 
        T0.DocEntry, 
        T0.DocNum, 
        T0.DocDate, 
        T0.CardCode, 
        T1.CardName, 
        T0.Address, 
        T0.drNo, 
        T0.NumAtCard, 
        T0.Ref1, 
        
        -- Sales Person Details
        T9.SlpName AS SalesPersonName,
        T0.SlpCode,
        
        T8.ItmsGrpNam AS ItemGroupName,
        T7.ItmsGrpCod,

        T2.DocNum AS RefSODocNum, 
        T5.DocNum AS RefSQDocNum,
        COALESCE(T2.DocNum, T5.DocNum) AS LinkedDocNum,

        COALESCE(T2.Ref1, T5.Ref1) AS RefSourceRef1, 
        COALESCE(T2.Ref2, T5.Ref2) AS RefSourceRef2,
        
        T4.BaseRef,
        T4.ItemCode, 
        T4.Dscription,
        T4.Quantity,
        T4.Price,
        
        COALESCE(T2.DocTotal, T5.DocTotal) AS SourceDocTotal,
        COALESCE(T2.VatSum, T5.VatSum) AS SourceVatSum
    FROM ODLN T0
    INNER JOIN DLN1 T4 ON T0.DocEntry = T4.DocEntry
    INNER JOIN OITM T7 ON T4.ItemCode = T7.ItemCode
    LEFT JOIN OITB T8 ON T7.ItmsGrpCod = T8.ItmsGrpCod
    LEFT JOIN OCRD T1 ON T0.CardCode = T1.CardCode
    
    -- Added join for Sales Person Name
    LEFT JOIN OSLP T9 ON T0.SlpCode = T9.SlpCode
    
    LEFT JOIN ORDR T2 ON T4.BaseEntry = T2.DocEntry AND T4.BaseType = 17
    LEFT JOIN OQUT T5 ON T4.BaseEntry = T5.DocEntry AND T4.BaseType = 23
    
    LEFT JOIN RDR1 T3 ON T4.BaseEntry = T3.DocEntry AND T4.BaseLine = T3.LineNum AND T4.BaseType = 17
    LEFT JOIN QUT1 T6 ON T4.BaseEntry = T6.DocEntry AND T4.BaseLine = T6.DocID AND T4.BaseType = 23
    
    /* Filtering logic */
    WHERE (T7.ItmsGrpCod = p_ItemGroupCode OR p_ItemGroupCode IS NULL)
   
    /* Sorting */
    ORDER BY T0.DocDate DESC, T0.DocNum DESC, T4.VisOrder ASC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `get_dr_with_sq_so_ref` */;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `get_dr_with_sq_so_ref`()
BEGIN
  SELECT 
        T0.DocEntry, 
        T0.DocNum, 
        T0.DocDate, 
        T0.CardCode, 
        T1.CardName, 
        T0.Address, 
        T0.drNo,
        T0.NumAtCard, 
        T0.Ref1, 
        T2.DocNum AS RefOrderDocNum, 
        T2.Ref1 AS RefOrderRef1, 
        T2.Ref2 AS RefOrderRef2,
        T3.ItemCode,
        T3.Dscription,
        T3.Quantity,
        T3.Price,
        T2.DocTotal,
        T2.VatSum
    FROM 
        ODLN T0
        LEFT JOIN OCRD T1 ON T1.CardCode = T0.CardCode
        LEFT JOIN ORDR T2 ON T2.DocEntry = T0.Ref1
        LEFT JOIN RDR1 T3 ON T3.DocEntry = T2.DocEntry
    ORDER BY 
        T0.DocDate DESC;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
/*!50003 DROP PROCEDURE IF EXISTS `Get_ItemStockStatus_ByDate` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `Get_ItemStockStatus_ByDate`(
    IN asOfDate DATE
)
BEGIN
    SELECT 
        i.ItemCode,
        i.OldItemCode,
        i.ItemName,
        i.ItmsGrpCod,
        i.invntryUom,
        i.BuyUnitMsr,
        i.SalUnitMsr,
        i.ManSerNum,
        i.ExitWh,
        b.BLDescription,
        i.Spec,

        IFNULL(po.OnPO, 0) AS OnPO,
        IFNULL(grpo.OnGRPO, 0) AS OnGRPO,
        IFNULL(gr.OnGR, 0) AS OnGR,
        IFNULL(so.OnSO, 0) AS OnSO,
        IFNULL(dr.OnDR, 0) AS OnDR,
        IFNULL(sr.OnSR, 0) AS OnSR,

        -- InStock formula (Based on transactions up to the date)
        (
            IFNULL(grpo.OnGRPO, 0)
            - IFNULL(gr.OnGR, 0)
            - IFNULL(dr.OnDR, 0)
            + IFNULL(sr.OnSR, 0)
        ) AS InStock,

        -- Available formula
        (
            (IFNULL(grpo.OnGRPO, 0)
            - IFNULL(gr.OnGR, 0)
            - IFNULL(dr.OnDR, 0)
            + IFNULL(sr.OnSR, 0)
            + IFNULL(po.OnPO, 0))
            - IFNULL(so.OnSO, 0)
        ) AS Available

    FROM OITM i
    INNER JOIN BINLOC b ON i.ExitWh = b.BLCode

    -- Purchase Orders (On Order)
    LEFT JOIN (
        SELECT t1.ItemCode, SUM(t1.Quantity) AS OnPO
        FROM POR1 t1
        INNER JOIN OPOR t0 ON t1.DocEntry = t0.DocEntry
        WHERE t0.DocDate <= asOfDate 
          AND (t1.LineStatus = 'O' OR t1.DocDate > asOfDate) -- Logic for historical "Open" status
        GROUP BY t1.ItemCode
    ) po ON po.ItemCode = i.ItemCode

    -- Goods Receipt PO (Add to Stock)
    LEFT JOIN (
        SELECT t1.ItemCode, SUM(t1.Quantity) AS OnGRPO
        FROM PDN1 t1
        INNER JOIN OPDN t0 ON t1.DocEntry = t0.DocEntry
        WHERE t0.DocDate <= asOfDate
        GROUP BY t1.ItemCode
    ) grpo ON grpo.ItemCode = i.ItemCode

    -- Goods Return (Subtract from Stock)
    LEFT JOIN (
        SELECT t1.ItemCode, SUM(t1.Quantity) AS OnGR
        FROM RPD1 t1
        INNER JOIN ORPD t0 ON t1.DocEntry = t0.DocEntry
        WHERE t0.DocDate <= asOfDate
        GROUP BY t1.ItemCode
    ) gr ON gr.ItemCode = i.ItemCode

    -- Sales Orders (Committed)
    LEFT JOIN (
        SELECT t1.ItemCode, SUM(t1.Quantity) AS OnSO
        FROM RDR1 t1
        INNER JOIN ORDR t0 ON t1.DocEntry = t0.DocEntry
        WHERE t0.DocDate <= asOfDate
          AND (t1.LineStatus = 'O' OR t1.DocDate > asOfDate)
        GROUP BY t1.ItemCode
    ) so ON so.ItemCode = i.ItemCode

    -- Deliveries (Subtract from Stock)
    LEFT JOIN (
        SELECT t1.ItemCode, SUM(t1.Quantity) AS OnDR
        FROM DLN1 t1
        INNER JOIN ODLN t0 ON t1.DocEntry = t0.DocEntry
        WHERE t0.DocDate <= asOfDate
        GROUP BY t1.ItemCode
    ) dr ON dr.ItemCode = i.ItemCode

    -- Returns (Add to Stock)
    LEFT JOIN (
        SELECT t1.ItemCode, SUM(t1.Quantity) AS OnSR
        FROM RDN1 t1
        INNER JOIN ORDN t0 ON t1.DocEntry = t0.DocEntry
        WHERE t0.DocDate <= asOfDate
        GROUP BY t1.ItemCode
    ) sr ON sr.ItemCode = i.ItemCode

    WHERE (
        (IFNULL(grpo.OnGRPO, 0)
        - IFNULL(gr.OnGR, 0)
        - IFNULL(dr.OnDR, 0)
        + IFNULL(sr.OnSR, 0)) != 0
    )

    ORDER BY i.ItmsGrpCod, i.Spec, i.ItemCode;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `Get_ItemStockStatus_Optimized` */;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `Get_ItemStockStatus_Optimized`()
BEGIN
    SELECT 
        i.ItemCode,
        i.OldItemCode,
        i.ItemName,
        i.ItmsGrpCod,
        i.invntryUom,
        i.BuyUnitMsr,
        i.SalUnitMsr,
        i.ManSerNum,
        i.ExitWh,
        b.BLDescription,
        i.Spec,

        IFNULL(po.OnPO, 0) AS OnPO,
        IFNULL(grpo.OnGRPO, 0) AS OnGRPO,
        IFNULL(gr.OnGR, 0) AS OnGR,
        IFNULL(so.OnSO, 0) AS OnSO,
        IFNULL(dr.OnDR, 0) AS OnDR,
        IFNULL(sr.OnSR, 0) AS OnSR,

        -- InStock formula
        (
            IFNULL(grpo.OnGRPO, 0)
            - IFNULL(gr.OnGR, 0)
            - IFNULL(dr.OnDR, 0)
            + IFNULL(sr.OnSR, 0)
        ) AS InStock,

        -- Available formula
        (
            (IFNULL(grpo.OnGRPO, 0)
            - IFNULL(gr.OnGR, 0)
            - IFNULL(dr.OnDR, 0)
            + IFNULL(sr.OnSR, 0)
            + IFNULL(po.OnPO, 0))
            - IFNULL(so.OnSO, 0)
        ) AS Available

    FROM OITM i
    INNER JOIN BINLOC b ON i.ExitWh = b.BLCode

    -- Pre-aggregated joins
    LEFT JOIN (
        SELECT ItemCode, SUM(OpenQty) AS OnPO
        FROM POR1
        WHERE LineStatus = 0
        GROUP BY ItemCode
    ) po ON po.ItemCode = i.ItemCode

    LEFT JOIN (
        SELECT ItemCode, SUM(Quantity) AS OnGRPO
        FROM PDN1
        WHERE LineStatus = 0
        GROUP BY ItemCode
    ) grpo ON grpo.ItemCode = i.ItemCode

    LEFT JOIN (
        SELECT ItemCode, SUM(Quantity) AS OnGR
        FROM RPD1
        WHERE LineStatus = 0
        GROUP BY ItemCode
    ) gr ON gr.ItemCode = i.ItemCode

    LEFT JOIN (
        SELECT ItemCode, SUM(OpenQty) AS OnSO
        FROM RDR1
        WHERE LineStatus = 0
        GROUP BY ItemCode
    ) so ON so.ItemCode = i.ItemCode

    LEFT JOIN (
        SELECT ItemCode, SUM(Quantity) AS OnDR
        FROM DLN1
        WHERE LineStatus = 0
        GROUP BY ItemCode
    ) dr ON dr.ItemCode = i.ItemCode

    LEFT JOIN (
        SELECT ItemCode, SUM(Quantity) AS OnSR
        FROM RDN1
        WHERE LineStatus = 0
        GROUP BY ItemCode
    ) sr ON sr.ItemCode = i.ItemCode

    WHERE (
        (IFNULL(grpo.OnGRPO, 0)
        - IFNULL(gr.OnGR, 0)
        - IFNULL(dr.OnDR, 0)
        + IFNULL(sr.OnSR, 0)) > 0
    )

    ORDER BY i.ItmsGrpCod, i.Spec, i.ItemCode;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
/*!50003 DROP PROCEDURE IF EXISTS `InsertApprovalTransaction` */;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `InsertApprovalTransaction`(
    IN pDocEntry INT,
    IN pObjType INT,
    IN pDocDate DATE,
    IN pStatus VARCHAR(1),
    IN pRemarks VARCHAR(255),
    IN pUserSign INT,
    IN pCreateDate DATE,
    IN pCreateTime VARCHAR(10),
    IN pIsDraft BOOLEAN,
    IN pApprovalDataJSON JSON,
    IN pApproversJSON JSON
)
BEGIN
    DECLARE vWddCode INT;

  

    START TRANSACTION;

    -- Insert into OWDD (only 1 row from approvalDataJSON)
    INSERT INTO OWDD (
        WtmCode, OwnerID, DocEntry, ObjType, DocDate, CurrStep, Status,
        Remarks, UserSign, CreateDate, CreateTime, IsDraft, MaxReqr
    )
    SELECT
        jt.WtmCode,
        jt.Originator,
        pDocEntry,
        pObjType,
        pDocDate,
        jt.WstCode,
        pStatus,
        pRemarks,
        pUserSign,
        pCreateDate,
        pCreateTime,
        pIsDraft,
        jt.MaxReqr
    FROM JSON_TABLE(pApprovalDataJSON, '$[*]'
        COLUMNS (
            WtmCode INT PATH '$.wtmCode',
            Originator INT PATH '$.originator',
            WstCode INT PATH '$.wstCode',
            MaxReqr INT PATH '$.maxReqr'
        )
    ) AS jt
    LIMIT 1;

    -- Get last inserted ID
    SET vWddCode = LAST_INSERT_ID();

    -- Insert into WDD1
    INSERT INTO WDD1 (
        WddCode, StepCode, UserID, Status, Remarks, UserSign, CreateDate, CreateTime
    )
    SELECT
        vWddCode,
        jt.WtmCode,
        jt.StageApprover,
        'W',
        jt.Remarks,
        pUserSign,
        pCreateDate,
        pCreateTime
    FROM JSON_TABLE(pApproversJSON, '$[*]'
        COLUMNS (
            WtmCode INT PATH '$.wtmCode',
            StageApprover INT PATH '$.stageApprover',
            Remarks VARCHAR(255) PATH '$.remarks'
        )
    ) AS jt;

    COMMIT;

    -- Return the inserted WddCode
    SELECT vWddCode AS WddCode;

END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
/*!50003 DROP PROCEDURE IF EXISTS `insertIntoOJDTAndReturnID` */;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `insertIntoOJDTAndReturnID`(
    IN pBaseRef VARCHAR(50),
    IN pMemo TEXT,
    IN pRef1 VARCHAR(50),
    IN pRef2 VARCHAR(50),
    IN pRefDate DATE,
    IN pLocTotal DECIMAL(18,2),
    IN pFCTotal DECIMAL(18,2),
    IN pSysTotal DECIMAL(18,2),
    IN pOrignCurr VARCHAR(10),
    IN pTransRate DECIMAL(18,6),
    IN pDueDate DATE,
    IN pTaxDate DATE,
    IN pFinncPriod INT,
    IN pCreateDate DATE,
    IN pUserSign INT
)
BEGIN
    -- Insert into OJDT table
    INSERT INTO OJDT (
        BaseRef, Memo, Ref1, Ref2, RefDate, LocTotal, FCTotal, SysTotal,
        OrignCurr, TransRate, DueDate, TaxDate, FinncPriod, CreateDate, UserSign
    )
    VALUES (
        pBaseRef, pMemo, pRef1, pRef2, pRefDate, pLocTotal, pFCTotal, pSysTotal,
        pOrignCurr, pTransRate, pDueDate, pTaxDate, pFinncPriod, pCreateDate, pUserSign
    );

    -- Return the last inserted ID
    SELECT LAST_INSERT_ID() AS transId;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
/*!50003 DROP PROCEDURE IF EXISTS `Insert_JDT1_Record` */;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_0900_ai_ci ;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `Insert_JDT1_Record`(
    IN pTransID INT,
    IN pShortName VARCHAR(100),
    IN pAccount VARCHAR(100),
    IN pDebit DECIMAL(18, 2),
    IN pCredit DECIMAL(18, 2),
    IN pFCDebit DECIMAL(18, 2),
    IN pFCCredit DECIMAL(18, 2),
    IN pFCCurrency VARCHAR(10),
    IN pRef1 VARCHAR(100),
    IN pRef2 VARCHAR(100),
    IN pRefDate DATE,
    IN pDueDate DATE,
    IN pTaxDate DATE,
    IN pProject VARCHAR(50),
    IN pVatGroup VARCHAR(20),
    IN pLineMemo VARCHAR(200),
    IN pContraAct VARCHAR(100)
)
BEGIN
    INSERT INTO JDT1 (
        TransID, ShortName, Account, Debit, Credit, FCDebit, FCCredit,
        FCCurrency, Ref1, Ref2, RefDate, DueDate, TaxDate,
        Project, VatGroup, LineMemo, ContraAct
    ) VALUES (
        pTransID, pShortName, pAccount, pDebit, pCredit, pFCDebit, pFCCredit,
        pFCCurrency, pRef1, pRef2, pRefDate, pDueDate, pTaxDate,
        pProject, pVatGroup, pLineMemo, pContraAct
    );
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
ALTER DATABASE `ultimau5_atilive` CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci ;
/*!50003 DROP PROCEDURE IF EXISTS `spGetContactInfo` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `spGetContactInfo`(
    IN pCardCode VARCHAR(50) CHARACTER SET utf8mb3 COLLATE utf8mb3_unicode_ci
)
BEGIN
    SELECT 
        OCRD.CardCode, 
        OCRD.CardName, 
        OCRD.CardType, 
        OCRD.Address, 
        OCRD.CntctPrsn, 
        OCPR.CntctCode, 
        OCPR.Name AS ContactName, 
        OCPR.Address AS ContactAddress,
        OCPR.E_MailL,
        OCPR.Tel1,
        OCPR.Tel2,
        OCRD.LicTradNum, 
        OCRD.ListNum, 
        OCRD.Currency, 
        OCRD.GroupNum, 
        
        OCTG.PymntGroup, -- Standard SAP B1 field name
        OCRD.Discount, 
        OCRD.SlpCode, 
        OSLP.SlpName, 
        OCRD.Balance, 
        OCRD.ECVatGroup, 
        OVTG.Code AS VatCode, 
        OVTG.Name AS VatName, 
        OVTG.Rate AS Rate, 
        OVTG.Account AS VatAccount, 
        OCRD.wtCode AS WTCode, 
        OWHT.WTName, 
        OWHT.Rate AS WTRate, 
        OWHT.Account AS WTAccount 
    FROM OCRD 
    LEFT JOIN OCPR ON OCRD.CardCode = OCPR.CardCode 
        AND OCRD.CntctPrsn = OCPR.Name
    LEFT JOIN OCTG ON OCRD.GroupNum = OCTG.GroupNum 
    LEFT JOIN OVTG ON OCRD.ECVatGroup = OVTG.Code 
    LEFT JOIN OSLP ON OCRD.SlpCode = OSLP.SlpCode 
    LEFT JOIN OWHT ON OCRD.wtCode = OWHT.wtCode 
    WHERE OCRD.CardCode COLLATE utf8mb3_unicode_ci = pCardCode;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_AutoApproveInternalSales` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_AutoApproveInternalSales`(
    IN p_CardCode VARCHAR(20),
    IN p_DocEntry INT
)
BEGIN
    DECLARE v_WddCode INT;
    DECLARE v_BotID INT DEFAULT 48;
    DECLARE v_DocType INT DEFAULT 11;

    -- 1. Locate the WddCode
    SELECT WddCode INTO v_WddCode 
    FROM OWDD 
    WHERE DocEntry = p_DocEntry 
      AND ObjType = v_DocType 
      AND Status = 'W' 
    LIMIT 1;

    -- 2. Execute auto-approval
    IF v_WddCode IS NOT NULL AND p_CardCode = 'S00722' THEN
        
        -- Update OQUT
        UPDATE OPOR SET WddStatus = 'Y' WHERE DocEntry = p_DocEntry;

        -- Update OWDD
        UPDATE OWDD SET Status = 'Y' WHERE WddCode = v_WddCode;

        -- Update WDD1 (Matching your column names: UserID, UpdateDate, UpdateTime)
        UPDATE WDD1 
        SET 
            Status = 'Y', 
            UserID = v_BotID, -- Updating the ID to the Bot
            UpdateDate = CURDATE(),
            UpdateTime = DATE_FORMAT(NOW(), '%H:%i:%s'),
            Remarks = 'Internal Sales: Auto-approved by auto.bot'
        WHERE WddCode = v_WddCode 
          AND Status = 'W'; -- Only update the lines currently waiting
        
    END IF;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_BatchProcessApprovalLogic` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_BatchProcessApprovalLogic`()
BEGIN
    -- 1. Insert into OWDD (Approval Header)
    INSERT INTO OWDD (
        DocEntry, ObjType, WtmCode, UserSign, OwnerID, 
        Status, CreateDate, CreateTime, IsDraft, DocDate, 
        CurrStep, MaxReqr, Remarks
    )
    SELECT 
        T0.DocEntry, 
        2,                  
        OWTM.WtmCode, 
        T0.UserSign, 
        T0.UserSign,        
        'W',                
        CURDATE(), 
        REPLACE(CAST(CURTIME() AS CHAR), ':', ''), 
        1,
        T0.DocDate,
        WTM2.WstCode,       
        OWST.MaxReqr,       
        OWTM.Name        
    FROM OPOR T0
    INNER JOIN WTM1 ON T0.UserSign = WTM1.UserID 
    INNER JOIN OWTM ON WTM1.WtmCode = OWTM.WtmCode 
    INNER JOIN WTM3 ON OWTM.WtmCode = WTM3.WtmCode AND WTM3.TransType = 2 
    INNER JOIN WTM4 ON OWTM.WtmCode = WTM4.WtmCode 
    INNER JOIN WTM2 ON OWTM.WtmCode = WTM2.WtmCode 
    INNER JOIN OWST ON WTM2.WstCode = OWST.WstCode 
    WHERE 
        OWTM.Active = 1     
        AND T0.WddStatus = 'W' 
        AND NOT EXISTS (SELECT 1 FROM OWDD WHERE OWDD.DocEntry = T0.DocEntry AND OWDD.ObjType = 2)
    -- Added all selected columns to GROUP BY to satisfy ONLY_FULL_GROUP_BY
    GROUP BY 
        T0.DocEntry, 
        OWTM.WtmCode, 
        T0.UserSign, 
        T0.DocDate, 
        WTM2.WstCode, 
        OWST.MaxReqr, 
        OWTM.Name
   HAVING COUNT(WTM4.CondId) = SUM(
    CASE 
        WHEN WTM4.opCode IS NULL THEN 1 -- Allows templates without conditions to pass
        WHEN WTM4.opCode = 1 AND CAST(T0.DocTotal AS DECIMAL(19,6)) > WTM4.opValue THEN 1
        WHEN WTM4.opCode = 2 AND CAST(T0.DocTotal AS DECIMAL(19,6)) < WTM4.opValue THEN 1
        WHEN WTM4.opCode = 3 AND CAST(T0.DocTotal AS DECIMAL(19,6)) = WTM4.opValue THEN 1
        WHEN WTM4.opCode = 4 AND CAST(T0.DocTotal AS DECIMAL(19,6)) >= WTM4.opValue THEN 1
        WHEN WTM4.opCode = 5 AND CAST(T0.DocTotal AS DECIMAL(19,6)) <= WTM4.opValue THEN 1 
        ELSE 0
    END
);
    -- 2. Insert into WDD1 (Approvers from Stage Members)
    INSERT INTO WDD1 (WddCode, StepCode, UserID, Status, CreateDate, CreateTime) 
    SELECT 
        OWDD.WddCode, 
        OWDD.WtmCode,        
        WST1.UserID,         
        'W',
        CURDATE(),
        REPLACE(CAST(CURTIME() AS CHAR), ':', '')
    FROM OWDD
    INNER JOIN WTM2 ON OWDD.WtmCode = WTM2.WtmCode 
    INNER JOIN WST1 ON WTM2.WstCode = WST1.WstCode 
    WHERE OWDD.Status = 'W' 
      AND NOT EXISTS (SELECT 1 FROM WDD1 WHERE WDD1.WddCode = OWDD.WddCode);
      
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_BatchProcessApprovalLogic2` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_BatchProcessApprovalLogic2`()
BEGIN
    -- 1. Insert into OWDD (Approval Header)
    INSERT INTO OWDD (
        DocEntry, ObjType, WtmCode, UserSign, OwnerID, 
        Status, CreateDate, CreateTime, IsDraft, DocDate, 
        CurrStep, MaxReqr, Remarks
    )
    SELECT 
        DocEntry, ObjType, WtmCode, UserSign, OwnerID, 
        Status, CreateDate, CreateTime, IsDraft, DocDate, 
        WstCode, MaxReqr, Name
    FROM (
        SELECT 
            T0.DocEntry, 
            2 AS ObjType,                  
            OWTM.WtmCode, 
            T0.UserSign, 
            T0.UserSign AS OwnerID,        
            'W' AS Status,                
            CURDATE() AS CreateDate, 
            REPLACE(CAST(CURTIME() AS CHAR), ':', '') AS CreateTime, 
            1 AS IsDraft,
            T0.DocDate,
            WTM2.WstCode,       
            OWST.MaxReqr,       
            OWTM.Name,
            -- Priority Logic: Rank templates with conditions (non-null) higher than 'auto-pass' templates
            ROW_NUMBER() OVER (
                PARTITION BY T0.DocEntry 
                ORDER BY (CASE WHEN WTM4.opCode IS NOT NULL THEN 0 ELSE 1 END) ASC, OWTM.WtmCode DESC
            ) as TemplateRank
        FROM OPOR T0
        INNER JOIN WTM1 ON T0.UserSign = WTM1.UserID 
        INNER JOIN OWTM ON WTM1.WtmCode = OWTM.WtmCode 
        INNER JOIN WTM3 ON OWTM.WtmCode = WTM3.WtmCode AND WTM3.TransType = 2 
        INNER JOIN WTM4 ON OWTM.WtmCode = WTM4.WtmCode 
        INNER JOIN WTM2 ON OWTM.WtmCode = WTM2.WtmCode 
        INNER JOIN OWST ON WTM2.WstCode = OWST.WstCode 
        WHERE 
            OWTM.Active = 1     
            AND T0.WddStatus = 'W' 
            AND NOT EXISTS (SELECT 1 FROM OWDD WHERE OWDD.DocEntry = T0.DocEntry AND OWDD.ObjType = 2)
        GROUP BY 
            T0.DocEntry, OWTM.WtmCode, T0.UserSign, T0.DocDate, WTM2.WstCode, OWST.MaxReqr, OWTM.Name, WTM4.opCode
        HAVING COUNT(WTM4.CondId) = SUM(
            CASE 
                WHEN WTM4.opCode IS NULL THEN 1 
                WHEN WTM4.opCode = 1 AND CAST(T0.DocTotal AS DECIMAL(19,6)) > WTM4.opValue THEN 1
                WHEN WTM4.opCode = 2 AND CAST(T0.DocTotal AS DECIMAL(19,6)) < WTM4.opValue THEN 1
                WHEN WTM4.opCode = 3 AND CAST(T0.DocTotal AS DECIMAL(19,6)) = WTM4.opValue THEN 1
                WHEN WTM4.opCode = 4 AND CAST(T0.DocTotal AS DECIMAL(19,6)) >= WTM4.opValue THEN 1
                WHEN WTM4.opCode = 5 AND CAST(T0.DocTotal AS DECIMAL(19,6)) <= WTM4.opValue THEN 1 
                ELSE 0
            END
        )
    ) AS RankedTemplates
    WHERE TemplateRank = 1; -- Only take the top-priority template match

    -- 2. Insert into WDD1 (Approvers from Stage Members)
    INSERT INTO WDD1 (WddCode, StepCode, UserID, Status, CreateDate, CreateTime) 
    SELECT 
        OWDD.WddCode, 
        OWDD.CurrStep,        
        WST1.UserID,         
        'W',
        CURDATE(),
        REPLACE(CAST(CURTIME() AS CHAR), ':', '')
    FROM OWDD
    INNER JOIN WST1 ON OWDD.CurrStep = WST1.WstCode 
    WHERE OWDD.Status = 'W' 
      AND NOT EXISTS (SELECT 1 FROM WDD1 WHERE WDD1.WddCode = OWDD.WddCode);
      
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_BatchProcessApprovalLogic3` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_BatchProcessApprovalLogic3`()
BEGIN
    -- 1. Insert into OWDD (Approval Header)
    INSERT INTO OWDD (
        DocEntry, ObjType, WtmCode, UserSign, OwnerID, 
        Status, CreateDate, CreateTime, IsDraft, DocDate, 
        CurrStep, MaxReqr, Remarks
    )
    SELECT 
        DocEntry, 2, WtmCode, UserSign, UserSign, 
        'W', CURDATE(), CreateTime, 1, DocDate, 
        WstCode, MaxReqr, Name
    FROM (
        SELECT 
            T0.DocEntry, 
            OWTM.WtmCode, 
            T0.UserSign, 
            REPLACE(CAST(CURTIME() AS CHAR), ':', '') AS CreateTime, 
            T0.DocDate,
            WTM2.WstCode,       
            OWST.MaxReqr,       
            OWTM.Name,
            -- RANKING: Prioritize templates with actual conditions (opCode 1-5) 
            -- over templates where conditions are NULL (auto-pass)
            ROW_NUMBER() OVER (
                PARTITION BY T0.DocEntry 
                ORDER BY (CASE WHEN WTM4.opCode IS NOT NULL THEN 0 ELSE 1 END) ASC, OWTM.WtmCode DESC
            ) as TemplateRank
        FROM OPOR T0
        INNER JOIN WTM1 ON T0.UserSign = WTM1.UserID 
        INNER JOIN OWTM ON WTM1.WtmCode = OWTM.WtmCode 
        -- Matches your WTM3 setup for TransType 2
        INNER JOIN WTM3 ON OWTM.WtmCode = WTM3.WtmCode AND WTM3.TransType = 2 
        INNER JOIN WTM4 ON OWTM.WtmCode = WTM4.WtmCode 
        INNER JOIN WTM2 ON OWTM.WtmCode = WTM2.WtmCode 
        INNER JOIN OWST ON WTM2.WstCode = OWST.WstCode 
        WHERE 
            OWTM.Active = 1     
            AND T0.WddStatus = 'W' -- Only pick documents "Waiting" for approval
            AND T0.DocType = 2    -- Your specific filter for Purchase Orders
            AND NOT EXISTS (SELECT 1 FROM OWDD WHERE OWDD.DocEntry = T0.DocEntry AND OWDD.ObjType = 2)
        GROUP BY 
            T0.DocEntry, OWTM.WtmCode, T0.UserSign, T0.DocDate, WTM2.WstCode, OWST.MaxReqr, OWTM.Name, WTM4.opCode, WTM4.opValue
        HAVING COUNT(WTM4.CondId) = SUM(
            CASE 
                WHEN WTM4.opCode IS NULL THEN 1 -- FIX: Allows Doc 738/739 to pass WtmCode 2
                WHEN WTM4.opCode = 1 AND CAST(T0.DocTotal AS DECIMAL(19,6)) > WTM4.opValue THEN 1
                WHEN WTM4.opCode = 2 AND CAST(T0.DocTotal AS DECIMAL(19,6)) < WTM4.opValue THEN 1
                WHEN WTM4.opCode = 3 AND CAST(T0.DocTotal AS DECIMAL(19,6)) = WTM4.opValue THEN 1
                WHEN WTM4.opCode = 4 AND CAST(T0.DocTotal AS DECIMAL(19,6)) >= WTM4.opValue THEN 1
                WHEN WTM4.opCode = 5 AND CAST(T0.DocTotal AS DECIMAL(19,6)) <= WTM4.opValue THEN 1 
                ELSE 0
            END
        )
    ) AS RankedTemplates
    WHERE TemplateRank = 1; -- Ensures 1 PO = 1 Approval Request

    -- 2. Insert into WDD1 (Approvers/Stages)
    INSERT INTO WDD1 (WddCode, StepCode, UserID, Status, CreateDate, CreateTime) 
    SELECT 
        OWDD.WddCode, 
        OWDD.CurrStep,        
        WST1.UserID,         
        'W',
        CURDATE(),
        REPLACE(CAST(CURTIME() AS CHAR), ':', '')
    FROM OWDD
    INNER JOIN WST1 ON OWDD.CurrStep = WST1.WstCode 
    WHERE OWDD.Status = 'W' 
      AND NOT EXISTS (SELECT 1 FROM WDD1 WHERE WDD1.WddCode = OWDD.WddCode);
      
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_BatchProcessApprovalLogic4` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_BatchProcessApprovalLogic4`()
BEGIN
    -- 1. Insert into OWDD (Approval Header)
    -- We use a subquery to rank multiple potential template matches for a single document
    INSERT INTO OWDD (
        DocEntry, ObjType, WtmCode, UserSign, OwnerID, 
        Status, CreateDate, CreateTime, IsDraft, DocDate, 
        CurrStep, MaxReqr, Remarks
    )
    SELECT 
        DocEntry, 
        2,              -- ObjType (Hardcoded to 2 for your Appsmith schema)
        WtmCode, 
        UserSign, 
        UserSign,       -- OwnerID
        'W',            -- Status 'W' for Waiting
        CURDATE(), 
        REPLACE(CAST(CURTIME() AS CHAR), ':', ''), 
        1,              -- IsDraft
        DocDate, 
        WstCode, 
        MaxReqr, 
        Name
    FROM (
        SELECT 
            T0.DocEntry, 
            OWTM.WtmCode, 
            T0.UserSign, 
            T0.DocDate,
            WTM2.WstCode,       
            OWST.MaxReqr,       
            OWTM.Name,
            -- RANKING LOGIC:
            -- If Template 2 is Inactive, this will only find Templates 126/127.
            -- It partitions by DocEntry so each PO only gets ONE approval entry.
            ROW_NUMBER() OVER (
                PARTITION BY T0.DocEntry 
                ORDER BY (CASE WHEN WTM4.opCode IS NOT NULL THEN 0 ELSE 1 END) ASC, OWTM.WtmCode DESC
            ) as TemplateRank
        FROM OPOR T0
        INNER JOIN WTM1 ON T0.UserSign = WTM1.UserID 
        INNER JOIN OWTM ON WTM1.WtmCode = OWTM.WtmCode 
        INNER JOIN WTM3 ON OWTM.WtmCode = WTM3.WtmCode AND WTM3.TransType = 2 
        INNER JOIN WTM4 ON OWTM.WtmCode = WTM4.WtmCode 
        INNER JOIN WTM2 ON OWTM.WtmCode = WTM2.WtmCode 
        INNER JOIN OWST ON WTM2.WstCode = OWST.WstCode 
        WHERE 
            OWTM.Active = 1     -- Only processes templates you have marked as Active
            AND T0.WddStatus = 'W' 
            AND T0.DocType = 2  -- Filters specifically for Purchase Orders
            AND NOT EXISTS (SELECT 1 FROM OWDD WHERE OWDD.DocEntry = T0.DocEntry AND OWDD.ObjType = 2)
        GROUP BY 
            T0.DocEntry, OWTM.WtmCode, T0.UserSign, T0.DocDate, WTM2.WstCode, OWST.MaxReqr, OWTM.Name, WTM4.opCode, WTM4.opValue
        HAVING COUNT(WTM4.CondId) = SUM(
            CASE 
                -- Allows templates with no specific monetary conditions to pass
                WHEN WTM4.opCode IS NULL THEN 1 
                -- Evaluates 738 (>50k) and 739 (<=50k)
                WHEN WTM4.opCode = 1 AND CAST(T0.DocTotal AS DECIMAL(19,6)) > WTM4.opValue THEN 1
                WHEN WTM4.opCode = 2 AND CAST(T0.DocTotal AS DECIMAL(19,6)) < WTM4.opValue THEN 1
                WHEN WTM4.opCode = 3 AND CAST(T0.DocTotal AS DECIMAL(19,6)) = WTM4.opValue THEN 1
                WHEN WTM4.opCode = 4 AND CAST(T0.DocTotal AS DECIMAL(19,6)) >= WTM4.opValue THEN 1
                WHEN WTM4.opCode = 5 AND CAST(T0.DocTotal AS DECIMAL(19,6)) <= WTM4.opValue THEN 1 
                ELSE 0
            END
        )
    ) AS RankedTemplates
    WHERE TemplateRank = 1; -- Ensures only the best-fit template is chosen

    -- 2. Insert into WDD1 (Approvers based on the chosen Step)
    INSERT INTO WDD1 (WddCode, StepCode, UserID, Status, CreateDate, CreateTime) 
    SELECT 
        OWDD.WddCode, 
        OWDD.CurrStep,        -- Uses the Step Code (Stage) selected in the first insert
        WST1.UserID,         
        'W',
        CURDATE(),
        REPLACE(CAST(CURTIME() AS CHAR), ':', '')
    FROM OWDD
    INNER JOIN WST1 ON OWDD.CurrStep = WST1.WstCode 
    WHERE OWDD.Status = 'W' 
      AND NOT EXISTS (SELECT 1 FROM WDD1 WHERE WDD1.WddCode = OWDD.WddCode);
      
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_BulkUpdateApprovalStatus` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_BulkUpdateApprovalStatus`()
BEGIN
    -- 1. Update OWDD (Headers)
    -- Updates only those OWDD records that are not yet 'Y' 
    -- but have at least 2 'Y' statuses in their corresponding WDD1 lines.
    UPDATE OWDD t1
    SET t1.Status = 'Y'
    WHERE t1.Status != 'Y' 
      AND (
        SELECT COUNT(*) 
        FROM WDD1 t2 
        WHERE t2.WddCode = t1.WddCode AND t2.Status = 'Y'
      ) >= 2;

    -- 2. Update OPOR (Purchase Orders)
    -- Updates OPOR records linked to the OWDD records we just marked as 'Y'.
    -- We use a JOIN to ensure we only update the specific POs that passed the approval hurdle.
    UPDATE OPOR t1
    INNER JOIN OWDD t2 ON t1.DocEntry = t2.DocEntry
    SET t1.WddStatus = 'Y'
    WHERE t2.Status = 'Y' 
      AND t1.WddStatus != 'Y';
      
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_CancelApprovalStatus` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_CancelApprovalStatus`(IN p_Wdd1ID INT)
BEGIN
    DECLARE v_WddCode INT;
    DECLARE v_DocEntry INT;

    -- 1. Get the WddCode from the specific line before updating
    SELECT WddCode INTO v_WddCode 
    FROM WDD1 
    WHERE Wdd1ID = p_Wdd1ID;

    IF v_WddCode IS NOT NULL THEN
        -- 2. Update the specific line in WDD1 to 'N'
        UPDATE WDD1 
        SET Status = 'N' 
        WHERE Wdd1ID = p_Wdd1ID;

        -- 3. Force the Header (OWDD) to 'N'
        UPDATE OWDD 
        SET Status = 'N' 
        WHERE WddCode = v_WddCode;

        -- 4. Get the DocEntry to update the Purchase Order
        SELECT DocEntry INTO v_DocEntry 
        FROM OWDD 
        WHERE WddCode = v_WddCode 
        LIMIT 1;

        -- 5. Update the Purchase Order (OPOR) to 'N'
        IF v_DocEntry IS NOT NULL THEN
            UPDATE OPOR 
            SET WddStatus = 'N' 
            WHERE DocEntry = v_DocEntry;
        END IF;
    END IF;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_CancelFullApproval` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_CancelFullApproval`(IN p_WddCode INT)
BEGIN
    DECLARE v_DocEntry INT;
    DECLARE v_CurrentDocStatus TINYINT(1);

    -- 1. Find the associated DocEntry and its current Status from OPOR
    SELECT a.DocEntry, b.DocStatus 
    INTO v_DocEntry, v_CurrentDocStatus
    FROM OWDD a
    INNER JOIN OPOR b ON a.DocEntry = b.DocEntry
    WHERE a.WddCode = p_WddCode
    LIMIT 1;

    -- 2. Only proceed if the Document is found and is still OPEN (Status = 0)
    IF v_DocEntry IS NOT NULL AND v_CurrentDocStatus = 0 THEN
        
        -- Mark ALL lines in WDD1 for this process as 'N'
        UPDATE WDD1 
        SET Status = 'N' 
        WHERE WddCode = p_WddCode;

        -- Update the Header (OWDD) to 'N'
        UPDATE OWDD 
        SET Status = 'N' 
        WHERE WddCode = p_WddCode;

        -- Sync the 'N' status to the Purchase Order (OPOR)
        UPDATE OPOR 
        SET WddStatus = 'N' 
        WHERE DocEntry = v_DocEntry;
        
    ELSEIF v_CurrentDocStatus = 1 THEN
        -- Optional: Raise an error or signal if trying to cancel a closed PO
        SIGNAL SQLSTATE '45000' 
        SET MESSAGE_TEXT = 'Cancellation denied: The Purchase Order is already Closed.';
    END IF;

END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_CheckPOApproval` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_CheckPOApproval`(
    IN p_UserSign INT,      -- The ID of the user creating the PO
    IN p_DocTotal DECIMAL(19,6), 
    IN p_ObjType INT        -- For Purchase Orders, usually 22
)
BEGIN
    -- Select templates where the user is an originator and conditions are met
    SELECT DISTINCT t0.WtmCode, t0.Name
    FROM OWTM t0
    INNER JOIN WTM1 t1 ON t0.WtmCode = t1.WtmCode
    INNER JOIN WTM3 t3 ON t0.WtmCode = t3.WtmCode
    LEFT JOIN WTM4 t4 ON t0.WtmCode = t4.WtmCode
    WHERE t0.Active = 1
      AND t1.UserID = p_UserSign
      AND t3.TransType = p_ObjType
      AND (
          -- If no conditions are defined in WTM4, it's an "Always Approve" rule
          t4.WTM4Id IS NULL 
          OR 
          -- Logic for Condition: Total Document (Assuming CondId 1 is DocTotal)
          (t4.CondId = 1 AND t4.opCode = 1 AND p_DocTotal > CAST(t4.opValue AS DECIMAL(19,6))) -- Greater Than
          OR
          (t4.CondId = 1 AND t4.opCode = 2 AND p_DocTotal < CAST(t4.opValue AS DECIMAL(19,6))) -- Less Than
          OR
          (t4.CondId = 1 AND t4.opCode = 3 AND p_DocTotal = CAST(t4.opValue AS DECIMAL(19,6))) -- Equal To
      );
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_OPOR_ReopenApproval` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_OPOR_ReopenApproval`(IN p_WddCode INT)
BEGIN
    DECLARE v_DocEntry INT;
    DECLARE v_CurrentDocStatus TINYINT(1);

    -- 1. Identify the document and its current status
    SELECT a.DocEntry, b.DocStatus 
    INTO v_DocEntry, v_CurrentDocStatus
    FROM OWDD a
    INNER JOIN OPOR b ON a.DocEntry = b.DocEntry
    WHERE a.WddCode = p_WddCode
    LIMIT 1;

    -- 2. Only allow re-opening if the document is still OPEN (0)
    -- We don't want to re-approve something that is already Closed/Invoiced (1)
    IF v_DocEntry IS NOT NULL AND v_CurrentDocStatus = 0 THEN
        
        -- Reset all decision lines to 'W' (Waiting)
        UPDATE WDD1 
        SET Status = 'W', 
            UpdateDate = CURDATE(), 
            UpdateTime = CURTIME()
        WHERE WddCode = p_WddCode;

        -- Reset Approval Header
        UPDATE OWDD 
        SET Status = 'W' 
        WHERE WddCode = p_p_WddCode;

        -- Reset Purchase Order Status
        UPDATE OPOR 
        SET WddStatus = 'W' 
        WHERE DocEntry = v_DocEntry;

    ELSEIF v_CurrentDocStatus = 1 THEN
        SIGNAL SQLSTATE '45000' 
        SET MESSAGE_TEXT = 'Error: Cannot re-open approval for a CLOSED Purchase Order.';
    END IF;

END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_ProcessApprovalLogic` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_ProcessApprovalLogic`(
    IN pDocEntry INT,
    IN puserId INT,
    IN pDocType INT,
    IN pDocTotal DECIMAL(19,6)
)
BEGIN
    -- 1. Declare a variable to hold the triggered Template Code
    DECLARE triggeredWtmCode INT;

    -- 2. Find the FIRST active template that matches ALL conditions
    SELECT OWTM.WtmCode INTO triggeredWtmCode
    FROM OWTM 
    INNER JOIN WTM1 ON OWTM.WtmCode = WTM1.WtmCode
    INNER JOIN WTM3 ON WTM3.WtmCode = OWTM.WtmCode
    INNER JOIN WTM4 ON WTM4.WtmCode = OWTM.WtmCode
    WHERE OWTM.Active = 'Y' 
      AND WTM1.UserID = puserId
      AND WTM3.TransType = pDocType
    GROUP BY OWTM.WtmCode
    HAVING COUNT(WTM4.CondId) = SUM(
        CASE 
            WHEN WTM4.opCode = 1 AND pDocTotal > WTM4.opValue THEN 1
            WHEN WTM4.opCode = 2 AND pDocTotal < WTM4.opValue THEN 1
            WHEN WTM4.opCode = 3 AND pDocTotal = WTM4.opValue THEN 1
            WHEN WTM4.opCode = 4 AND pDocTotal >= WTM4.opValue THEN 1
            WHEN WTM4.opCode = 5 AND pDocTotal <= WTM4.opValue THEN 1
            ELSE 0
        END
    )
    LIMIT 1;

    -- 3. If a template was triggered, perform the insertions
    IF triggeredWtmCode IS NOT NULL THEN
        
        -- Insert into Header (OWDD)
        INSERT INTO OWDD (DocEntry, ObjType, WtmCode, UserSign, Status, CreateDate, CreateTime, IsDraft)
        VALUES (pDocEntry, pDocType, triggeredWtmCode, puserId, 'W', CURDATE(), REPLACE(CURTIME(),':',''), 'Y');

        -- Get the ID of the record just created
        SET @lastWddCode = LAST_INSERT_ID();

        -- Insert all Approvers linked to this template stage (WDD1)
        INSERT INTO WDD1 (WddCode, StepCode, UserCode, Status)
        SELECT @lastWddCode, WTM2.StepCode, WTM2.UserID, 'W'
        FROM WTM2
        WHERE WTM2.WtmCode = triggeredWtmCode;
        
    END IF;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_SyncHeaderAndDoc` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_SyncHeaderAndDoc`(IN p_WddCode INT)
BEGIN
    DECLARE v_ApprovedCount INT DEFAULT 0;
    DECLARE v_TotalAssigned INT DEFAULT 0;
    DECLARE v_PendingCount INT DEFAULT 0;
    DECLARE v_MaxReqr INT DEFAULT 1;
    DECLARE v_DocEntry INT;
    DECLARE v_DocStatus TINYINT(1);

    -- 1. Check approval counts in WDD1
    SELECT 
        COUNT(CASE WHEN Status = 'Y' THEN 1 END),
        COUNT(*),
        COUNT(CASE WHEN Status != 'Y' THEN 1 END)
    INTO 
        v_ApprovedCount,
        v_TotalAssigned,
        v_PendingCount
    FROM WDD1
    WHERE WddCode = p_WddCode;

    -- 2. Retrieve MaxReqr from OWST (fallback to OWDD.MaxReqr or total lines)
    SELECT 
        COALESCE(st.MaxReqr, a.MaxReqr, v_TotalAssigned, 1),
        a.DocEntry, 
        b.DocStatus 
    INTO 
        v_MaxReqr,
        v_DocEntry, 
        v_DocStatus
    FROM OWDD a
    LEFT JOIN OWST st ON a.CurrStep = st.WstCode
    INNER JOIN OPOR b ON a.DocEntry = b.DocEntry
    WHERE a.WddCode = p_WddCode
    LIMIT 1;

    -- 3. ONLY approve if:
    --    - Approved count meets or exceeds MaxReqr
    --    - NO pending lines remain (v_PendingCount = 0), OR you strictly require all assigned approvers
    --    - The PO is still open (DocStatus = 0)
    IF v_ApprovedCount >= v_MaxReqr 
       AND v_PendingCount = 0 
       AND v_TotalAssigned > 0 
       AND v_DocStatus = 0 THEN
        
        -- Mark Header Approved
        UPDATE OWDD 
        SET Status = 'Y' 
        WHERE WddCode = p_WddCode;

        -- Mark PO Document Approved
        IF v_DocEntry IS NOT NULL THEN
            UPDATE OPOR 
            SET WddStatus = 'Y' 
            WHERE DocEntry = v_DocEntry;
        END IF;
        
    END IF;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_SyncHeaderAndDoc_Active` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_SyncHeaderAndDoc_Active`(IN p_WddCode INT)
BEGIN
    DECLARE v_ApprovedCount INT;
    DECLARE v_TotalNeeded INT;
    DECLARE v_DocEntry INT;
    DECLARE v_DocStatus INT;

    SELECT 
        COUNT(CASE WHEN Status = 'Y' THEN 1 END),
        COUNT(*)
    INTO v_ApprovedCount, v_TotalNeeded
    FROM WDD1
    WHERE WddCode = p_WddCode;

    SELECT 
        a.DocEntry, 
        b.DocStatus 
    INTO v_DocEntry, v_DocStatus
    FROM OWDD a
    INNER JOIN OPOR b ON a.DocEntry = b.DocEntry
    WHERE a.WddCode = p_WddCode
    LIMIT 1;

    IF v_ApprovedCount >= v_TotalNeeded 
       AND v_TotalNeeded > 0 
       AND v_DocStatus = 0 THEN

        UPDATE OWDD 
        SET Status = 'Y' 
        WHERE WddCode = p_WddCode;

        IF v_DocEntry IS NOT NULL THEN
            UPDATE OPOR 
            SET WddStatus = 'Y' 
            WHERE DocEntry = v_DocEntry;
        END IF;

    END IF;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_SyncHeaderAndDoc_Force` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_SyncHeaderAndDoc_Force`(IN p_WddCode INT, IN p_NewStatus CHAR(1))
BEGIN
    DECLARE v_DocEntry INT;
    DECLARE v_DocStatus TINYINT(1);

    -- Get Doc Info
    SELECT a.DocEntry, b.DocStatus 
    INTO v_DocEntry, v_DocStatus
    FROM OWDD a
    INNER JOIN OPOR b ON a.DocEntry = b.DocEntry
    WHERE a.WddCode = p_WddCode
    LIMIT 1;

    -- Only update if the PO is still Open (0)
    IF v_DocEntry IS NOT NULL AND v_DocStatus = 0 THEN
        -- Update Header
        UPDATE OWDD SET Status = p_NewStatus WHERE WddCode = p_WddCode;
        
        -- Update Purchase Order
        UPDATE OPOR SET WddStatus = p_NewStatus WHERE DocEntry = v_DocEntry;
    END IF;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_UpdateApprovalStatus` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_UpdateApprovalStatus`(IN p_WddCode INT)
BEGIN
    DECLARE v_ApprovedCount INT;
    DECLARE v_DocEntry INT;

    -- 1. Check how many 'Y' statuses exist in WDD1 for this WddCode
    SELECT COUNT(*) INTO v_ApprovedCount
    FROM WDD1
    WHERE WddCode = p_WddCode AND Status = 'Y';

    -- 2. If 2 or more 'Y' values are found, proceed with updates
    IF v_ApprovedCount >= 2 THEN
        
        -- Update the OWDD Header Status to 'Y'
        UPDATE OWDD 
        SET Status = 'Y' 
        WHERE WddCode = p_WddCode;

        -- Get the DocEntry associated with this WddCode to update OPOR
        SELECT DocEntry INTO v_DocEntry 
        FROM OWDD 
        WHERE WddCode = p_WddCode 
        LIMIT 1;

        -- Update the OPOR table status
        IF v_DocEntry IS NOT NULL THEN
            UPDATE OPOR 
            SET WddStatus = 'Y' 
            WHERE DocEntry = v_DocEntry;
        END IF;
        
    END IF;
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;
/*!50003 DROP PROCEDURE IF EXISTS `sp_VerifyPOConditions` */;
/*!50003 SET @saved_cs_client      = @@character_set_client */ ;
/*!50003 SET @saved_cs_results     = @@character_set_results */ ;
/*!50003 SET @saved_col_connection = @@collation_connection */ ;
/*!50003 SET character_set_client  = utf8mb4 */ ;
/*!50003 SET character_set_results = utf8mb4 */ ;
/*!50003 SET collation_connection  = utf8mb4_0900_ai_ci */ ;
/*!50003 SET @saved_sql_mode       = @@sql_mode */ ;
/*!50003 SET sql_mode              = 'ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION' */ ;
DELIMITER ;;
CREATE DEFINER=`ultimau5_jvmacuh`@`%` PROCEDURE `sp_VerifyPOConditions`(
    IN p_DocEntry INT
)
BEGIN
    -- This query finds if the specific PO matches ANY approval template 
    -- based on the conditions defined in WTM4.
    SELECT DISTINCT t0.WtmCode, t0.Name AS TemplateName
    FROM OWTM t0
    INNER JOIN WTM1 t1 ON t0.WtmCode = t1.WtmCode -- Originators
    INNER JOIN WTM3 t3 ON t0.WtmCode = t3.WtmCode -- Object Type (PO = 22)
    INNER JOIN WTM4 t4 ON t0.WtmCode = t4.WtmCode -- Conditions
    INNER JOIN OPOR p  ON p.UserSign = t1.UserID  -- The PO being checked
    WHERE p.DocEntry = p_DocEntry
      AND t0.Active = 1
      AND t3.TransType = 22
      AND (
          -- Condition 1: DocTotal (Assuming CondId 1 is Total)
          (t4.CondId = 1 AND t4.opCode = 1 AND p.DocTotal > CAST(t4.opValue AS DECIMAL(19,6))) OR -- Greater Than
          (t4.CondId = 1 AND t4.opCode = 2 AND p.DocTotal < CAST(t4.opValue AS DECIMAL(19,6))) OR -- Less Than
          
          -- Condition 2: Discount Percent (Assuming CondId 2 is Discount)
          (t4.CondId = 2 AND t4.opCode = 1 AND p.DiscPrcnt > CAST(t4.opValue AS DECIMAL(19,6))) OR
          
          -- Condition 3: Gross Profit (Assuming CondId 3 is GP)
          (t4.CondId = 3 AND t4.opCode = 2 AND p.GrosProfit < CAST(t4.opValue AS DECIMAL(19,6)))
      );
END ;;
DELIMITER ;
/*!50003 SET sql_mode              = @saved_sql_mode */ ;
/*!50003 SET character_set_client  = @saved_cs_client */ ;
/*!50003 SET character_set_results = @saved_cs_results */ ;
/*!50003 SET collation_connection  = @saved_col_connection */ ;

--
-- Final view structure for view `approval_mapping`
--

/*!50001 DROP VIEW IF EXISTS `approval_mapping`*/;
/*!50001 SET @saved_cs_client          = @@character_set_client */;
/*!50001 SET @saved_cs_results         = @@character_set_results */;
/*!50001 SET @saved_col_connection     = @@collation_connection */;
/*!50001 SET character_set_client      = utf8mb4 */;
/*!50001 SET character_set_results     = utf8mb4 */;
/*!50001 SET collation_connection      = utf8mb4_0900_ai_ci */;
/*!50001 CREATE ALGORITHM=UNDEFINED */
/*!50013 DEFINER=`ultimau5_jvmacuh`@`%` SQL SECURITY DEFINER */
/*!50001 VIEW `approval_mapping` AS select `U`.`FNAME` AS `FNAME`,`U`.`LNAME` AS `LNAME`,`W`.`WstCode` AS `WstCode`,`O`.`Name` AS `Name`,`O`.`Remarks` AS `Remarks`,`O`.`MaxReqr` AS `MaxReqr` from ((`WST1` `W` join `USER` `U` on((`W`.`UserID` = `U`.`USER_ID`))) join `OWST` `O` on((`O`.`WstCode` = `W`.`WstCode`))) order by `O`.`WstCode` */;
/*!50001 SET character_set_client      = @saved_cs_client */;
/*!50001 SET character_set_results     = @saved_cs_results */;
/*!50001 SET collation_connection      = @saved_col_connection */;

--
-- Final view structure for view `bin_stock`
--

/*!50001 DROP VIEW IF EXISTS `bin_stock`*/;
/*!50001 SET @saved_cs_client          = @@character_set_client */;
/*!50001 SET @saved_cs_results         = @@character_set_results */;
/*!50001 SET @saved_col_connection     = @@collation_connection */;
/*!50001 SET character_set_client      = utf8mb4 */;
/*!50001 SET character_set_results     = utf8mb4 */;
/*!50001 SET collation_connection      = utf8mb4_unicode_ci */;
/*!50001 CREATE ALGORITHM=UNDEFINED */
/*!50013 DEFINER=`ultimau5_jvmacuh`@`%` SQL SECURITY DEFINER */
/*!50001 VIEW `bin_stock` AS select `i`.`ItemCode` AS `ItemCode`,`i`.`ItemName` AS `ItemName`,`w`.`WhsCode` AS `WhsCode`,`w`.`WhsName` AS `WhsName`,`b`.`AbsEntry` AS `BinAbs`,`b`.`BinCode` AS `BinCode`,ifnull(sum(`q`.`OnHandQty`),0) AS `OnHand` from (((`OITM` `i` join `OWHS` `w`) join `OBIN` `b` on((`b`.`WhsCode` = `w`.`WhsCode`))) left join `OIBQ` `q` on(((`q`.`ItemCode` = `i`.`ItemCode`) and (`q`.`BinAbs` = `b`.`AbsEntry`)))) group by `i`.`ItemCode`,`b`.`AbsEntry` */;
/*!50001 SET character_set_client      = @saved_cs_client */;
/*!50001 SET character_set_results     = @saved_cs_results */;
/*!50001 SET collation_connection      = @saved_col_connection */;

--
-- Final view structure for view `inventory_ledger`
--

/*!50001 DROP VIEW IF EXISTS `inventory_ledger`*/;
/*!50001 SET @saved_cs_client          = @@character_set_client */;
/*!50001 SET @saved_cs_results         = @@character_set_results */;
/*!50001 SET @saved_col_connection     = @@collation_connection */;
/*!50001 SET character_set_client      = utf8mb4 */;
/*!50001 SET character_set_results     = utf8mb4 */;
/*!50001 SET collation_connection      = utf8mb4_unicode_ci */;
/*!50001 CREATE ALGORITHM=UNDEFINED */
/*!50013 DEFINER=`ultimau5_jvmacuh`@`%` SQL SECURITY DEFINER */
/*!50001 VIEW `inventory_ledger` AS select (convert(`gr`.`ItemCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `ItemCode`,(convert(`gr`.`WhsCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `WhsCode`,`o`.`DocDate` AS `DocDate`,('GRPO' collate utf8mb4_unicode_ci) AS `TransType`,`o`.`DocEntry` AS `DocEntry`,`o`.`DocNum` AS `DocNum`,`gr`.`VisOrder` AS `LineIdentifier`,`gr`.`Quantity` AS `InQty`,cast(0 as decimal(19,6)) AS `OutQty` from (`PDN1` `gr` join `OPDN` `o` on((`o`.`DocEntry` = `gr`.`DocEntry`))) where (ifnull(`o`.`CANCELED`,'N') = 'N') union all select (convert(`rp`.`ItemCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_10`,(convert(`rp`.`WhsCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `CONVERT(``rp``.``WhsCode`` USING utf8mb4) COLLATE utf8mb4_unicode_ci`,`o`.`DocDate` AS `DocDate`,('G-RET' collate utf8mb4_unicode_ci) AS `'G-RET' COLLATE utf8mb4_unicode_ci`,`o`.`DocEntry` AS `DocEntry`,`o`.`DocNum` AS `DocNum`,`rp`.`VisOrder` AS `VisOrder`,cast(0 as decimal(19,6)) AS `CAST(0 AS DECIMAL(19,6))`,`rp`.`Quantity` AS `Quantity` from (`RPD1` `rp` join `ORPD` `o` on((`o`.`DocEntry` = `rp`.`DocEntry`))) where (ifnull(`o`.`CANCELED`,'N') = 'N') union all select (convert(`gi`.`ItemCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_19`,(convert(`gi`.`WhsCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `CONVERT(``gi``.``WhsCode`` USING utf8mb4) COLLATE utf8mb4_unicode_ci`,`o`.`DocDate` AS `DocDate`,('GI' collate utf8mb4_unicode_ci) AS `'GI' COLLATE utf8mb4_unicode_ci`,`o`.`DocEntry` AS `DocEntry`,`o`.`DocNum` AS `DocNum`,`gi`.`LineNum` AS `LineNum`,cast(0 as decimal(19,6)) AS `CAST(0 AS DECIMAL(19,6))`,`gi`.`Quantity` AS `Quantity` from (`IGE1` `gi` join `OIGE` `o` on((`o`.`DocEntry` = `gi`.`DocEntry`))) where (ifnull(`o`.`CANCELED`,'N') = 'N') union all select (convert(`ign`.`ItemCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_28`,(convert(`ign`.`WhsCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_29`,`o`.`DocDate` AS `DocDate`,('GR' collate utf8mb4_unicode_ci) AS `'GR' COLLATE utf8mb4_unicode_ci`,`o`.`DocEntry` AS `DocEntry`,`o`.`DocNum` AS `DocNum`,`ign`.`LineNum` AS `LineNum`,`ign`.`Quantity` AS `Quantity`,cast(0 as decimal(19,6)) AS `CAST(0 AS DECIMAL(19,6))` from (`IGN1` `ign` join `OIGN` `o` on((`o`.`DocEntry` = `ign`.`DocEntry`))) where (ifnull(`o`.`CANCELED`,'N') = 'N') union all select (convert(`tr`.`ItemCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_37`,(convert(`tr`.`WhsCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `CONVERT(``tr``.``WhsCode`` USING utf8mb4) COLLATE utf8mb4_unicode_ci`,`o`.`DocDate` AS `DocDate`,('TR-IN' collate utf8mb4_unicode_ci) AS `'TR-IN' COLLATE utf8mb4_unicode_ci`,`o`.`DocEntry` AS `DocEntry`,`o`.`DocNum` AS `DocNum`,`tr`.`LineNum` AS `LineNum`,`tr`.`Quantity` AS `Quantity`,cast(0 as decimal(19,6)) AS `CAST(0 AS DECIMAL(19,6))` from (`WTR1` `tr` join `OWTR` `o` on((`o`.`DocEntry` = `tr`.`DocEntry`))) where (ifnull(`o`.`CANCELED`,'N') = 'N') union all select (convert(`tr`.`ItemCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_46`,(convert(`tr`.`FromWhsCod` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_47`,`o`.`DocDate` AS `DocDate`,('TR-OUT' collate utf8mb4_unicode_ci) AS `'TR-OUT' COLLATE utf8mb4_unicode_ci`,`o`.`DocEntry` AS `DocEntry`,`o`.`DocNum` AS `DocNum`,`tr`.`LineNum` AS `LineNum`,cast(0 as decimal(19,6)) AS `CAST(0 AS DECIMAL(19,6))`,`tr`.`Quantity` AS `Quantity` from (`WTR1` `tr` join `OWTR` `o` on((`o`.`DocEntry` = `tr`.`DocEntry`))) where (ifnull(`o`.`CANCELED`,'N') = 'N') union all select (convert(`dl`.`ItemCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_55`,(convert(`dl`.`WhsCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `CONVERT(``dl``.``WhsCode`` USING utf8mb4) COLLATE utf8mb4_unicode_ci`,`o`.`DocDate` AS `DocDate`,('DLV' collate utf8mb4_unicode_ci) AS `'DLV' COLLATE utf8mb4_unicode_ci`,`o`.`DocEntry` AS `DocEntry`,`o`.`DocNum` AS `DocNum`,`dl`.`LineNum` AS `LineNum`,cast(0 as decimal(19,6)) AS `CAST(0 AS DECIMAL(19,6))`,`dl`.`Quantity` AS `Quantity` from (`DLN1` `dl` join `ODLN` `o` on((`o`.`DocEntry` = `dl`.`DocEntry`))) where (ifnull(`o`.`CANCELED`,'N') = 'N') union all select (convert(`rd`.`ItemCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_64`,(convert(`rd`.`WhsCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `CONVERT(``rd``.``WhsCode`` USING utf8mb4) COLLATE utf8mb4_unicode_ci`,`o`.`DocDate` AS `DocDate`,('RET' collate utf8mb4_unicode_ci) AS `'RET' COLLATE utf8mb4_unicode_ci`,`o`.`DocEntry` AS `DocEntry`,`o`.`DocNum` AS `DocNum`,`rd`.`LineNum` AS `LineNum`,`rd`.`Quantity` AS `Quantity`,cast(0 as decimal(19,6)) AS `CAST(0 AS DECIMAL(19,6))` from (`RDN1` `rd` join `ORDN` `o` on((`o`.`DocEntry` = `rd`.`DocEntry`))) where (ifnull(`o`.`CANCELED`,'N') = 'N') union all select (convert(`inv`.`ItemCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_73`,(convert(`inv`.`WhsCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_74`,`o`.`DocDate` AS `DocDate`,('AR-INV' collate utf8mb4_unicode_ci) AS `'AR-INV' COLLATE utf8mb4_unicode_ci`,`o`.`DocEntry` AS `DocEntry`,`o`.`DocNum` AS `DocNum`,`inv`.`LineNum` AS `LineNum`,cast(0 as decimal(19,6)) AS `CAST(0 AS DECIMAL(19,6))`,`inv`.`Quantity` AS `Quantity` from (`INV1` `inv` join `OINV` `o` on((`o`.`DocEntry` = `inv`.`DocEntry`))) where ((ifnull(`o`.`CANCELED`,'N') = 'N') and (`inv`.`BaseType` <> 15)) union all select (convert(`rin`.`ItemCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_82`,(convert(`rin`.`WhsCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_83`,`o`.`DocDate` AS `DocDate`,('AR-CM' collate utf8mb4_unicode_ci) AS `'AR-CM' COLLATE utf8mb4_unicode_ci`,`o`.`DocEntry` AS `DocEntry`,`o`.`DocNum` AS `DocNum`,`rin`.`LineNum` AS `LineNum`,`rin`.`Quantity` AS `Quantity`,cast(0 as decimal(19,6)) AS `CAST(0 AS DECIMAL(19,6))` from (`RIN1` `rin` join `ORIN` `o` on((`o`.`DocEntry` = `rin`.`DocEntry`))) where ((ifnull(`o`.`CANCELED`,'N') = 'N') and (`rin`.`BaseType` <> 16)) union all select (convert(`pch`.`ItemCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_91`,(convert(`pch`.`WhsCode` using utf8mb4) collate utf8mb4_unicode_ci) AS `Name_exp_92`,`o`.`DocDate` AS `DocDate`,('AP-INV' collate utf8mb4_unicode_ci) AS `'AP-INV' COLLATE utf8mb4_unicode_ci`,`o`.`DocEntry` AS `DocEntry`,`o`.`DocNum` AS `DocNum`,`pch`.`VisOrder` AS `VisOrder`,`pch`.`Quantity` AS `Quantity`,cast(0 as decimal(19,6)) AS `CAST(0 AS DECIMAL(19,6))` from (`PCH1` `pch` join `OPCH` `o` on((`o`.`DocEntry` = `pch`.`DocEntry`))) where ((ifnull(`o`.`CANCELED`,'N') = 'N') and (`pch`.`BaseType` <> 20)) */;
/*!50001 SET character_set_client      = @saved_cs_client */;
/*!50001 SET character_set_results     = @saved_cs_results */;
/*!50001 SET collation_connection      = @saved_col_connection */;

--
-- Final view structure for view `item_master`
--

/*!50001 DROP VIEW IF EXISTS `item_master`*/;
/*!50001 SET @saved_cs_client          = @@character_set_client */;
/*!50001 SET @saved_cs_results         = @@character_set_results */;
/*!50001 SET @saved_col_connection     = @@collation_connection */;
/*!50001 SET character_set_client      = utf8mb4 */;
/*!50001 SET character_set_results     = utf8mb4 */;
/*!50001 SET collation_connection      = utf8mb4_unicode_ci */;
/*!50001 CREATE ALGORITHM=UNDEFINED */
/*!50013 DEFINER=`ultimau5_jvmacuh`@`%` SQL SECURITY DEFINER */
/*!50001 VIEW `item_master` AS select `OITM`.`ItemCode` AS `ItemCode`,`OITM`.`ItemName` AS `ItemName`,`OITM`.`ItmsGrpCod` AS `ItmsGrpCod`,`OITM`.`InvntItem` AS `InvntItem`,`OITM`.`SalUnitMsr` AS `SalUnitMsr`,`OITM`.`BuyUnitMsr` AS `BuyUnitMsr`,`OITM`.`ManSerNum` AS `ManSerNum`,`OITM`.`ManBtchNum` AS `ManBtchNum`,`OITM`.`Spec` AS `Spec` from `OITM` */;
/*!50001 SET character_set_client      = @saved_cs_client */;
/*!50001 SET character_set_results     = @saved_cs_results */;
/*!50001 SET collation_connection      = @saved_col_connection */;

--
-- Final view structure for view `item_stock`
--

/*!50001 DROP VIEW IF EXISTS `item_stock`*/;
/*!50001 SET @saved_cs_client          = @@character_set_client */;
/*!50001 SET @saved_cs_results         = @@character_set_results */;
/*!50001 SET @saved_col_connection     = @@collation_connection */;
/*!50001 SET character_set_client      = utf8mb4 */;
/*!50001 SET character_set_results     = utf8mb4 */;
/*!50001 SET collation_connection      = utf8mb4_unicode_ci */;
/*!50001 CREATE ALGORITHM=UNDEFINED */
/*!50013 DEFINER=`ultimau5_jvmacuh`@`%` SQL SECURITY DEFINER */
/*!50001 VIEW `item_stock` AS select `i`.`ItemCode` AS `ItemCode`,`i`.`ItemName` AS `ItemName`,`i`.`ItmsGrpCod` AS `ItmsGrpCod`,`i`.`InvntItem` AS `invntryUom`,`i`.`Spec` AS `Spec`,`w`.`WhsCode` AS `WhsCode`,`w`.`WhsName` AS `WhsName`,(((ifnull(sum(`gr`.`Quantity`),0) - ifnull(sum(`gi`.`Quantity`),0)) + ifnull(sum(`trf_in`.`Quantity`),0)) - ifnull(sum(`trf_out`.`Quantity`),0)) AS `OnHand`,ifnull(sum(`po`.`OpenQty`),0) AS `OnPO`,ifnull(sum(`so`.`OpenQty`),0) AS `OnSO`,(((((ifnull(sum(`gr`.`Quantity`),0) - ifnull(sum(`gi`.`Quantity`),0)) + ifnull(sum(`trf_in`.`Quantity`),0)) - ifnull(sum(`trf_out`.`Quantity`),0)) + ifnull(sum(`po`.`OpenQty`),0)) - ifnull(sum(`so`.`OpenQty`),0)) AS `Available` from (((((((`OITM` `i` join `OWHS` `w`) left join `PDN1` `gr` on(((`i`.`ItemCode` = `gr`.`ItemCode`) and (`gr`.`WhsCode` = `w`.`WhsCode`) and (`gr`.`LineStatus` = 'O')))) left join `IGE1` `gi` on(((`i`.`ItemCode` = `gi`.`ItemCode`) and (`gi`.`WhsCode` = `w`.`WhsCode`) and (`gi`.`LineStatus` = 'O')))) left join `WTR1` `trf_in` on(((`i`.`ItemCode` = `trf_in`.`ItemCode`) and (`trf_in`.`WhsCode` = `w`.`WhsCode`)))) left join `WTR1` `trf_out` on(((`i`.`ItemCode` = `trf_out`.`ItemCode`) and (`trf_out`.`FromWhsCod` = `w`.`WhsCode`)))) left join `POR1` `po` on(((`i`.`ItemCode` = `po`.`ItemCode`) and (`po`.`WhsCode` = `w`.`WhsCode`) and (`po`.`LineStatus` = 'O')))) left join `RDR1` `so` on(((`i`.`ItemCode` = `so`.`ItemCode`) and (`so`.`WhsCode` = `w`.`WhsCode`) and (`so`.`LineStatus` = 'O')))) group by `i`.`ItemCode`,`w`.`WhsCode` */;
/*!50001 SET character_set_client      = @saved_cs_client */;
/*!50001 SET character_set_results     = @saved_cs_results */;
/*!50001 SET collation_connection      = @saved_col_connection */;
/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE */;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;

-- Dump completed on 2026-09-25 10:17:26
